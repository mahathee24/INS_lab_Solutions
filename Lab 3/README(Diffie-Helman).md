Diffie-Hellman Key Exchange Algorithm
  This Python program implements the Diffie-Hellman key exchange algorithm, which allows two parties (Alice and Bob) to securely share a secret key over an insecure communication channel.

Steps in the program:

Inputs:

    A prime number q is chosen.
    A primitive root a modulo q is selected.
     Each party (Alice and Bob) generates their private keys Xa and Xb.
Public Keys:

    Alice computes her public key Ya = a^Xa % q.
     Bob computes his public key Yb = a^Xb % q.
    Shared Secret Key:

    Alice calculates the shared key Ka = Yb^Xa % q.
    Bob computes the shared key Kb = Ya^Xb % q.
Output:

    The public keys of Alice and Bob are displayed.
    The shared secret keys of Alice and Bob are printed. Both keys (Ka and Kb) should be identical if the algorithm is executed correctly.
