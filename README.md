# PingID

- [Installation and Setup](#download-pingid-for-windows)  
- [PingID Integration for Windows Login](#pingid-integration-for-windows-login)  
- [PingID Integration for Mac Login](#pingid-integration-for-mac-login)  
- [Mobile App (iOS & Android)](#mobile-app-ios--android)  
- [Integration Kit for PingFederate](#integration-kit-for-pingfederate)


## Download PingID for Windows

**⬇️ [Download PingID Windows Installer](*)**

PingID installation involves downloading the appropriate integration package (Windows, macOS, or server platform). Setup requires:

* `pingid.properties` file (generated from the PingOne admin portal)
* Admin privileges
* Network access to PingID services
* GUI or CLI-based installers

> \[!note]
> For automated deployments (e.g., via SCCM or MDM), use the CLI installer with flags like `--silent` or `--very-silent`.

## PingID Integration for Windows Login

PingID for Windows enhances login security for local and RDP sessions.

### Features:

* MFA on initial login and screen unlock
* Support for password-based and passwordless login
* Offline authentication using paired devices or security keys
* Number matching and push authentication
* FIDO2 key support (v2.3+)

> \[!tip]
> PingID for Windows works only with machines acting as servers and verified Credential Providers (CP). PIN is not supported on Windows 10.

```bash
pingid_install.exe --silent --rsa_padding
```

## PingID Integration for Mac Login

PingID for Mac enforces MFA on macOS devices using a GUI or CLI installer.

### Supported Features:

* MFA for login and lock screen
* OAEP padding for offline encryption
* Network selection from lock screen
* Language localization (Czech, Polish, Hungarian)
* Compatibility with macOS 10.15+ (Monterey and newer)

> \[!warning]
> Versions 10.13 (High Sierra) and 10.14 (Mojave) are not supported.

## Mobile App (iOS & Android)

PingID offers dedicated mobile apps for both iOS and Android platforms, supporting:

* Push authentication
* Biometric authentication (Face ID, Touch ID)
* Offline OTP generation
* Watch support (Apple Watch)

### Highlights:

* iOS: Latest version 1.8.4
* Android: Latest version 3.2.0

> \[!note]
> Offline use requires at least one successful online pairing.

## Integration Kit for PingFederate

PingID integrates with PingFederate via an SDK adapter.

### Steps:

1. Install the PingID SDK Integration Kit
2. Configure a PingID adapter instance
3. Setup authentication policies and OpenID clients
4. Enable token management

> \[!info]
> Choose correct claim types (e.g., UPN vs. WindowsAccountName) during setup. This choice is **immutable** post-configuration.

## PingID Desktop App

The desktop app is an alternative when mobile devices are not available or not permitted.

### Functions:

* Local authentication approvals
* Secure offline token generation
* PIN-based desktop access control

> \[!tip]
> Automatic updates and policy-based enforcement available via admin settings.

## Passwordless Login Options

PingID supports multiple passwordless authentication flows:

* **Number matching** in mobile app
* **FIDO2** security keys
* **Offline OTP** with soft tokens

> \[!warning]
> A 2-minute lockout applies after 3 failed passwordless login attempts on Windows.

## SSH Integration

PingID can be configured to secure SSH access to Linux servers.

### Features:

* PAM module integration
* MFA prompts during SSH login
* TOTP, push, or FIDO2 authentication
* Command-line audit trails and fallback options

> \[!note]
> SSH integration setup may require root access and SSHD/PAM configuration.

## Release Notes & SDK Updates

PingID's development is active, with detailed release notes included per component:

* New CLI flags: `--silent`, `--rsa_padding`
* Enhanced support for Monterey (macOS)
* Push rate-limiting
* Offline support and FIPS updates
* Security fixes (e.g., CVE-2022-23717 mitigation)

> \[!example]
> **PID-5297** – Fixed group-based login bypass vulnerability in Windows Login
