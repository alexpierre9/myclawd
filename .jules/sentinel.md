## 2025-03-12 - [Disable Browser Evaluate by Default]
**Vulnerability:** Browser arbitrary code execution via the `/act` endpoint (Remote Code Execution) was enabled by default because `DEFAULT_BROWSER_EVALUATE_ENABLED` in `src/browser/constants.ts` defaulted to `true`.
**Learning:** Default configurations must be secure (fail securely). Allowing arbitrary script evaluation out-of-the-box introduces a significant attack surface and potential RCE.
**Prevention:** Always default security-sensitive features (like browser code evaluation) to `false` in configuration constants, and ensure Zod schemas enforce this default fallback when parsing optional configurations.
