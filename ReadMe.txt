Requirements:

    * openssl
    * base32 (from GNU coreutils)

You are recommended to use it with "pass" from http://www.passwordstore.org/

For example, to get the token for two-factor authentication:

    totp "$(pass show otp/GitHub)" GitHub

The third parameter "GitHub" is optional and defaults to "Google", since the
Google Authenticator app has become the de facto standard for such usage.
