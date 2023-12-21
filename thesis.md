

# thesis  


## CUDA implementation of WFA sequence alignment algorithm 

  Supervisor: [doc. RNDr. Jozef Jirásek, PhD.](https://www.upjs.sk/PF/zamestnanec/jozef.jirasek/)
  Advisor: [Biofyzik](www.biofyzika.sk)

Institute: [Department of Computer Science, Pavol Jozef Safarik University](https://ics.science.upjs.sk/)  
  
  Author: **Miroslav Kurka** 
- e-mail: _my first name dot my last name at student dot upjs dot sk_

 
## Research proposal 

Sequence aligmnet is one of the fundamental tool in bionformatics. It provdise a framework for studying the evolution of DNA, RNA, and proteins. Since the first sequence alignment algorithm was proposed in 1981 by Smith et. al.[5], there have been many improvements and new algorithms proposed [2,3,4]. However due to ever increasing amount of data, there is always a need for faster implementation or new approach to sequence alignment. Particulalry the advent of next-generation sequencing (NGS) has brought new challenges for sequence alignment algorithms[3]. One of the recent advances was the invention of the Wavefront algorithm (WFA) [1]. WFA is a gap-affine pairwise alignment algorithm that is based on the Smith-Waterman algorithm [1,6]. WFA compared to other S-W like algorithms, which run in quadratic time, has complexity of O(ns+s^2).  Furthuer reduction could be achieved by implementing it in CUDA as was proven in 2023 [2]. Goal of this thesis is to implement it in CUDA and compare the performance with other implementation[2].

//TODO add more info about WFA and why we choose it.

## Achievable goals

- [ ] Implement WFA in CUDA
- [ ] Compare performance with CPU implementation
- [ ] Compare performance with other GPU implementation 
- [ ] Code must be kept open-source and available on GitHub


## Full Thesis available:
(MOCK LINKS - NOT WORKING)
 - [source code](https://github.com/miroslavkurka/cuda-wfa-align)
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


[1] Santiago Marco-Sola, Juan Carlos Moure, Miquel Moreto, Antonio Espinosa, Fast gap-affine pairwise alignment using the wavefront algorithm, Bioinformatics, Volume 37, Issue 4, February 2021, Pages 456–463, https://doi.org/10.1093/bioinformatics/btaa777

[2] Aguado-Puig, Q. et al. (2023) ‘WFA-GPU: Gap-affine pairwise alignment using GPUs’. bioRxiv. Available at: https://doi.org/10.1101/2022.04.18.488374.


[3] Müller, A. et al. (2022) ‘Anyseq/gpu: a novel approach for faster sequence alignment on gpus’, in Proceedings of the 36th ACM International Conference on Supercomputing, pp. 1–11. Available at: https://doi.org/10.1145/3524059.3532376.

[4] Kim, J., Ji, M. and Yi, G. (2020) ‘A review on sequence alignment algorithms for short reads based on next-generation sequencing’, IEEE Access, 8, pp. 189811–189822. Available at: https://doi.org/10.1109/ACCESS.2020.3031159

[5] Michael Farrar, Striped Smith–Waterman speeds database searches six times over other SIMD implementations, Bioinformatics, Volume 23, Issue 2, January 2007, Pages 156–161, https://doi.org/10.1093/bioinformatics/btl582

[6] Smith, T.F. and Waterman, M.S. (1981) ‘Identification of common molecular subsequences’, Journal of Molecular Biology, 147(1), pp. 195–197. Available at: https://doi.org/10.1016/0022-2836(81)90087-5.



