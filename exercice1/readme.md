# Practical Reverse Engineering Solutions – Page 11
## problem :

![This is an image](images/exercice.png)

## Solution
01. EDI is a pointer to [ebp+8]
02. edx save the pointer of EDI in order to retrieve it whenever edi is changed
03. EAX =0(xor eax,eax => set eax to zero)
04. ecx = -1 (0fffffff =-1)
05. repne scasb ==> will scan bytes of a string until the end of string == Null , also repne scasb will use EDI as a pointer

### so answering to the first question [ebp+8] is pointer to a string (char*) 

06. ecx=ecx+2
07. ecx= -(ecx)
08. AL=[ebp+0Ch] (AL size is byte so logically it couldn't contain a pointer to a string or ahole adress but it contains some bits that make a ascii charcter also bcz of the STOS used after)
09. reset EDI with the orginal pointer stored in EDX
10. rep stosb ==> will copy what's on AL(ascii charcter) in each byte of the string in EDI(will end when ecx=0)

11. This copies the address of the string to EAX. EAX holds the return value of the function, so the snippet returns a pointer to the modified string.