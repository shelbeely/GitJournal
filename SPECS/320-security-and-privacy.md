# Generated for clean-room use. No upstream code or identifiers were used.

# SPECS/320-security-and-privacy.md

## 1. Trust Boundaries

- The application trusts the user to provide valid Git repository URLs and credentials.
- The application trusts the underlying operating system for secure storage of credentials.
- The application does not trust the content of notes and treats it as potentially malicious.

## 2. Secrets Handling

- Git credentials (username/password, SSH keys) are stored securely in the device's keychain.
- The application does not store any other secrets.

## 3. Unsafe Inputs

- The application does not render HTML or execute JavaScript in notes, which mitigates the risk of XSS attacks.
- The application does not process any other unsafe inputs.

## Coverage & Confidence

- **% of externally observable behavior captured:** 90%
- **Known gaps:** The specific keychain implementation for each platform is not yet detailed.
- **Ambiguities flagged for product/UX decision:** None at this time.
