---
layout: default
title: 0x001 - Cryptography
parent: Assignments
nav_order: 2
has_children: false
has_toc: true
permalink: /assignments/0x001-cryptography
---

# 0x001 - Cryptography

**Due at 11:59pm on October 27, 2022**

I'd recommend completing this assignment with Python, although you're welcome to use any language.

## Question 1 (6 points)

The following text has been encrypted with a [Caesar cipher](https://en.wikipedia.org/wiki/Caesar_cipher).

> Wflijtfiv reu jvmve pvrij rxf fli wrkyvij siflxyk wfiky, fe kyzj tfekzevek, r evn erkzfe, tfetvzmvu ze czsvikp, reu uvuztrkvu kf kyv gifgfjzkzfe kyrk rcc dve riv tivrkvu vhlrc. Efn nv riv vexrxvu ze r xivrk tzmzc nri, kvjkzex nyvkyvi kyrk erkzfe, fi rep erkzfe jf tfetvzmvu, reu jf uvuztrkvu, tre cfex veuliv. Nv riv dvk fe r xivrk srkkcv-wzvcu fw kyrk nri. Nv yrmv tfdv kf uvuztrkv r gfikzfe fw kyrk wzvcu, rj r wzerc ivjkzex-gcrtv wfi kyfjv nyf yviv xrmv kyvzi czmvj, kyrk kyrk erkzfe dzxyk czmv. Zk zj rckfxvkyvi wzkkzex reu gifgvi kyrk nv jyflcu uf kyzj. Slk, ze r crixvi jvejv, nv treefk uvuztrkv, nv treefk tfejvtirkv—nv treefk yrccfn—kyzj xifleu. Kyv sirmv dve, czmzex reu uvru, nyf jkilxxcvu yviv, yrmv tfejvtirkvu zk wri rsfmv fli gffi gfnvi kf ruu fi uvkirtk. Kyv nficu nzcc czkkcv efkv, efi cfex ivdvdsvi nyrk nv jrp yviv, slk zk tre evmvi wfixvk nyrk kyvp uzu yviv. Zk zj wfi lj kyv czmzex, irkyvi, kf sv uvuztrkvu yviv kf kyv lewzezjyvu nfib nyzty kyvp nyf wflxyk yviv yrmv kylj wri jf efscp rumretvu. Zk zj irkyvi wfi lj kf sv yviv uvuztrkvu kf kyv xivrk krjb ivdrzezex svwfiv lj—kyrk wifd kyvjv yfefivu uvru nv krbv zetivrjvu uvmfkzfe kf kyrk trljv wfi nyzty kyvp yviv xrmv kyv crjk wlcc dvrjliv fw uvmfkzfe—kyrk nv yviv yzxycp ivjfcmv kyrk kyvjv uvru jyrcc efk yrmv uzvu ze mrze—kyrk kyzj erkzfe, leuvi Xfu, jyrcc yrmv r evn sziky fw wivvufd, reu kyrk xfmviedvek fw kyv gvfgcv, sp kyv gvfgcv, wfi kyv gvfgcv, jyrcc efk gvizjy wifd kyv vriky.

### Question 1a (3 points)

Generate a letter frequency chart for this passage.

### Question 1b (2 points)

Compare the letter frequency of this passage to standard english.
Suggest the "shift".

### Question 1c (1 point)

Decrypt the message.

## Question 2 (8 points)

For this question, you'll encrypt and decrypt a message.
I recommend using a library for the actual encryption.
In class we used the `cryptography` [package](https://pypi.org/project/cryptography/).

### Encryption (3 points for code, 1 point for encrypted result)

Create a UTF-8 encoded string with your name and banner number: "Jane Doe - B00123456".
Encrypt it with AES-128 encryption in ECB mode with a private key of your choice.

### Decryption (3 points for code, 1 point for decrypted result)

Decrypt the secret message to recover your name and banner number.

## Question 3 (6 points)

In this question we'll explore checksums and hashes.

### Question 3a (2 points)

Write a simple "checksum" function that computes a hash for binary data by simply summing each byte.
Demonstrate your checksum function by computing the hash of your name + banner string from Question 2.

### Question 3b (4 points)

Why is this a bad approach to generating hashes?
What should you use instead?
Can you demonstrate with an example?

Pick a "good" hash function and compare it to the naive one you wrote in part a.
Hint: the `cryptography` package offers a number of "good" hash functions to choose from.
I don't expect you to implement these on your own.





