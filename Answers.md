## Vulernability Remediation:
### Vulnerability 1: 
1. Which package or library are you addressing?
I am addressing the `PyYAML` library.

2. Which CVE is linked to this vulnerability?
This is linked to CVE-2019-20477.

3. What remediation steps do you suggest? Strategic rec: Develop a vulnerability management program.

Tactical rec: Update the `PyYAML` package in the `requirements.txt` file to version 5.4 or higher. Additionally, replace any instances of the unsafe `yaml.load()` or `yaml.load_all()` functions with `yaml.safe_load()` in the application code. This vulnerability allows attackers to execute arbitrary system commands via a class deserialization issue if untrusted input is processed. For a technical breakdown of the `subprocess.Popen` exploit path, see the [National Vulnerability Database analysis](https://nvd.nist.gov/vuln/detail/cve-2019-20477).

### Vulnerability 2:
1. Which vulnerability are you addressing?
I am addressing a Remote Code Execution vulnerability in the `Pillow` package, specifically within the `PIL.ImageMath.eval` function.

2. Which CVE is linked to this vulnerability?
This is linked to CVE-2023-50447.

3. What remediation steps do you suggest? Strategic rec: Developer training for security by design.

Tactical rec: Upgrade the `Pillow` package in the `requirements.txt` file to version 10.2.0 or higher. The root cause is improper input validation (always sanitize input) within the `ImageMath.eval()` function's environment parameter, which allows attackers to inject callable Python objects into the evaluation context. After updating the version, rebuild the Docker image and re-run the GitHub Actions pipeline. For a detailed breakdown of the exploit mechanism, refer to [SentinelOne's Vulnerability Database](https://www.sentinelone.com/vulnerability-database/cve-2023-50447/).