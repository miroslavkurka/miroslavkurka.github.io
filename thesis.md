# /home/miro/thesis


## CUDA implementation of Crystals Dilithium 

  Supervisor: [doc. RNDr. Jozef Jirásek, PhD.](https://www.upjs.sk/PF/zamestnanec/jozef.jirasek/)

Institute: [Department of Computer Science, Pavol Jozef Safarik University](https://ics.science.upjs.sk/)  
  
  Author: **Miroslav Kurka** 
- e-mail: _my first name dot my last name at student dot upjs dot sk_


## Abstract 

Widely used cryptographic algorithms are based on the hardness of integer factorization and discrete logarithm problems. However, these problems can be solved efficiently by quantum computers. [1] Therefore, it is necessary to develop new cryptographic algorithms that are resistant to quantum computers. [1] One of the proposed algorithms resistant to attacks from quantum computers is proposed FIPS204 Crystals-Dilithium (ML-DSA), which is based on the hardness of the Shortest Vector Problem (SVP) in lattices. [2] NIST proposal was approved in 2023. [2].

//TODO: add more info about CPU GPU implementations

Since then there have been several implementations of this algorithm. [3, 4, 5]

//TODO: list reasons why we need GPU implementation

The aim of this thesis is to implement the Dilithium signature scheme in CUDA and compare the performance with other implementations. [3, 4, 5]


## Achievable goals

- [ ] Implement Dilithium signature scheme in CUDA
- [ ] Compare performance with CPU implementation
- [ ] Compare performance with other GPU implementations
- [ ] Code must be kept open-source and available on GitHub
- [ ] Host code must be MISRA-C compliant


## Full Thesis available:
(MOCK LINKS - NOT WORKING)
 - [thesis.pdf](thesis.pdf)
 - [thesis.tex](thesis.tex)
 - doi: [10.0000/arXiv.XXXX.Xx](google.com)

## Licensing 
MIT License

Copyright (c) 2023 Miroslav Kurka

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## References 

[1] Bernstein, D.J. and Lange, T. (2017) ‘Post-quantum cryptography’, Nature, 549(7671), pp. 188–194. Available at: https://doi.org/10.1038/nature23461.

[2] Technology, N.I. of S. and (2023) Module-Lattice-Based Digital Signature Standard. Federal Information Processing Standard (FIPS) 204 (Draft). U.S. Department of Commerce. Available at: https://doi.org/10.6028/NIST.FIPS.204.ipd.

[3] Lyubashevsky, V. (2009) ‘Fiat-Shamir with Aborts: Applications to Lattice and Factoring-Based Signatures’, in M. Matsui (ed.) Advances in Cryptology – ASIACRYPT 2009. Berlin, Heidelberg: Springer Berlin Heidelberg (Lecture Notes in Computer Science), pp. 598–616. Available at: https://doi.org/10.1007/978-3-642-10366-7_35.

[4] Seo, S.C. and An, S. (2023) ‘Parallel implementation of CRYSTALS-Dilithium for effective signing and verification in autonomous driving environment’, ICT Express, 9(1), pp. 100–105. Available at: https://doi.org/10.1016/j.icte.2022.08.003.


[5] Shen, S. et al. (2023) ‘High-Throughput GPU Implementation of Dilithium Post-Quantum Digital Signature’. arXiv. Available at: https://doi.org/10.48550/arXiv.2211.12265.



