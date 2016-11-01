## fix fatal error: 'openssl/rand.h' file not found

on osx when we install the: Crypt::OpenSSL::Random perl module, 
it's get error: **openssl/rand.h** file not found

simple to fix it:


    brew install openssl
    ln -s /usr/local/Cellar/openssl/1.0.2c/include/openssl /usr/local/include/openssl


that's it.  
