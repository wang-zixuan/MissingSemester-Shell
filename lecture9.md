Lecture 9: Security and Cryptography

1. Entropy (formula doesn't display properly on Github)

   - $entropy=4\times log_2100000=66.4 \; bits$

   - $entropy=8\times log_2(26+26+10)=48 \; bits$

   - The first one.

   - $t_1=2^{66}/10000=7.4\times10^{15}s, \; t_2=2^{48}/10000=2.8\times10^{10}s$

2. Symmetric cryptography

   ```shell
   openssl aes-256-cbc -pbkdf2 -in README.md -out README.enc.md
   cat README.enc.md
   openssl aes-256-cbc -pbkdf2 -d -in README.enc.md -out README.dec.md
   cmp README.md README.dec.md
   ```

4. Asymmetric

   ```shell
   ssh-keygen -t ed25519
   
   git commit -a -S -m 'signed commit'
   git show --show-signature
   ```

