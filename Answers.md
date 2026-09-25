## Vulernability Remediation:
### Vulnerability 1: 
1. Which package or library are you addressing?
I am addressing the `PyYAML` library.

2. Which CVE is linked to this vulnerability?
This is linked to CVE-2019-20477.

3. What remediation steps do you suggest?
Update the `PyYAML` package in the `requirements.txt` file to version 5.4 or higher. Additionally, developers must replace any instances of the unsafe `yaml.load()` function with `yaml.safe_load()` in the application code. After making these changes, rebuild the container image.

### Vulnerability 2:
1. Which vulnerability are you addressing?
I am addressing an Arbitrary Code Execution vulnerability in the `Pillow` package, specifically within the `PIL.ImageMath.eval` function.

2. Which CVE is linked to this vulnerability?
This is linked to CVE-2023-50447.

3. What remediation steps do you suggest?
Upgrade the `Pillow` package in the `requirements.txt` file to version 10.2.0 or higher, which patches the execution safeguards for the `ImageMath.eval` function. Rebuild the Docker image and re-run the GitHub Actions pipeline to verify the alert is cleared.