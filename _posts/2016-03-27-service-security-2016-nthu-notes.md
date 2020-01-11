---
layout: post
title: "Service Security 2016 NTHU Notes"
author: billy_rick
modified: 2016-08-28
comments: true
excerpt: "Service Security 2016 NTHU Notes"
tags: []
---

## Information Entropy
1. Privacy vs Security (Panopticon (Psychologically affect humans))
2. Information Security: Base 6 usage, can be used to represent a larger set of numbers.
3. The difficulty of compression: explain (Information is more valuabe based on how compressable it is/ not how meaningful it is to me)
4. Predictability & Compressability define the Entropy of Information
5. Wheather (atmospheric noise) -> the best way to randomize information
6. Zipf Law (use this law to see what is the entrop of a password for the most common words (20%))
7. Check what sites are using to check the password?


## Information Integrity
1. Constants can be initialized with a variable
2. Write your test first
3. Tests are a contract between your clients and your organization
4. Follow Test Driven Development (TDD)
5. Just write code that passes the tests
6. You make your code more beautiful after you have passed your tests
7. Analyze the problem, pass your tests, then write beautiful code
8. (Protobuffer):  to send very compressed data; very different from the transferring of JSON and XML types
9. Jumpee - Atom's plugin to jump around your code
10. [RuboCop](https://github.com/bbatsov/ruby-style-guide) - to check your code for violation of syntax uses in Ruby
11. Ruby methods are great (readable) if 5 lines of code are used.
12. Map / Reduce to iterate over arrays, etc., instead of for loops.
13. In order to understand how to get the most optimized code you must run benchmarks

Bonus:

~~~ ruby
# Ruby OOP Metaprogramming
attr_accessor

describe 'test' do
	it 'test body'
		# ...
	end
end

# minitest
xxx.must_equal true

~~~

Domain Specific Language (DSL)- looks like new code(methods) being embedded into a programming language

YAML: A form of serializing data

## Cryptography
1. Keyspace: all the possible spaces that's needed to cover the plaintext
2. Confusion: encrypt -> ciphertext
3. Diffusion:  plaintext -> encrypt -> ciphertext
4. Permutation: scramble cipher
5. High Diffusion doesn't necessarily mean High Confusions
6. A cipher is secure if there are no real (shortcuts) patterns.
7. Kerckhoff's Principle
8. Double Transposition Cipher: Problems with the size of column
9. One time pad: keep changing the key

## Cryptography Part B
1. SK-Cryptography: Stream Ciphers
2. RC4 operates with bytes and A5/1 Ciphers operate at bit level (more computational complexity)
3. Diffusion is low for A5/1 Ciphers
4. Diffusion keeps changing steadily
5. WEP weak because of CRC (Cyclic Redundancy Check)

## Asymmetric Cryptography
1. PK-Cryptography ensures confidentiality (Agent (securing) Handler)
2. PK-Cryptography ensures non-repudiation (Agent (signing) Handler)
3. First we sign then secure so that the other side decrypts and then remove the signature with Agents public key.
4. In the end it all boils down to one human problem: TRUST
5. The luhn validator is easy to check and easy to solve
5. All P problems and are NP Problems.

## Assignments ([Coded in Ruby](https://github.com/wisebits))
1. Luhn Algorithm
2. Permutation, Substitution and Double Transposition Ciphers
3. Advanced Cryptography and Hashing
