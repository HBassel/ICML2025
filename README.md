Dear Reviewers,
We ran additional experiments to better evaluate our MLMC compression method across difference tasks.
In this Anonymized GitHub repository you can find three folders, each corresponding to a different experimental setup as we elaborate below.

"BERT NLP Top-k Compression Experiments":
We evaulated our adaptive MLMC method using Top-k compression on the SST-2 benchmark using BERT finetuning. We used the AdamW optimizer.
The folder includes 2 files showcasing the accuracy vs. #Gbit communicated, and accuracy vs. iteration (number of steps), both for M=4 machines and for k={0.01n, 0.05n, 0.1n, 0.5n}.
We evaluated our MLMC method against EF21-SGDM, Top-k, Rand-k, and SGD (we keep this terminology, for clarity, with a slight abuse of notation, but note that the underlying optimizer for all is AdamW).

As is evident by these plots, our MLMC method enjoys the fastest convergence for the same #Gbit communicated, and it enjoys similar convergence to that of (uncompressed) SGD, and still performs better than other methods, for the same number of steps.
These results (in addition to the ones in the paper) prove a strong advantage and efficiency of our method compared to existing methods, both in communication efficiency and convergence rate, across vastly different tasks like CV and NLP.

"RESNET CIFAR-10 Fixed Point Compression Experiments":
We ran our MLMC method using Fixed-Point compression on CIFAR-10 using ResNet-18 against 2-bit FP, 2-bit QSGD, and (uncompressed) SGD.
The folder includes 2 files showcasing the accuracy vs. #Gbit and accuracy vs. iteration (both for M=4 and M=32 machines).

Our method enjoys the fastest convergence and highest accuracy. Although (uncompressed) SGD surpasses all methods after enough steps.

"RESNET CIFAR10 Top-k Compression Experiments":
We evaulated our adaptive MLMC method using Top-k compression on CIFAR-10 using ResNet-18 against EF21-SGDM, Top-k, Rand-k, and (uncompressed) SGD.
The folder includes 4 files showcasing the accuracy vs. #Gbit and accuracy vs. iteration (number of steps), both for M=4 machines and for k={0.01n, 0.05n, 0.1n, 0.5n}.

Our method enjoys a significant advantage over comparable methods in terms of communication efficiency, convergence speed, and final accuracy. Our method's advantage grows with the number of machines.
In the accuracy vs. iteration plots, uncompressed SGD eventually surpasses all methods, as expected, although our method is comparable when compression is not too extreme while other compression methods still experience performance degradation.

