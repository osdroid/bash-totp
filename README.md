## Requirements:
1) openssl  
2) base32 (from GNU coreutils)  

## PLEASE NOTE
I'm mostly playing with bash, and trying some tricks. The goal of this project isn't
to be better than the original, just my playground :)

## Approach
Each totp secret is encrypted separately in its own file.  
The encryption used is AES 256 CBC  
And to have an easier time finding them, they are all in the same folder
defined in the env variable TOTP_SECRETS_PATH  
The ./totp command will list all files under that folder, and add it temporarily
to the history, so that you can use the arrows to navigate through the options.

## How to set up
1) Decide where to store your totp secrets, maybe $HOME/.totp-secrets and mkdir that folder  
2) Then "export TOTP_SECRETS_PATH=/path/to/totp/secrets" (pro tip) add it to .bashrc  
3) Now add some "secrets"  
openssl enc -aes-256-cbc -a <<< 'otpauth secretinbase32eitherlowerORUPPER 30 6' > /path/to/totp/secrets/service1

## Usage: ./totp

