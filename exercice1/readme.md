# Practical Reverse Engineering Solutions – Page 11
## problem :
![This is an image](images/exercice.png)
- at first we need to know the type of [EBP+8] and [EBP+C]
to guess what the type of [EBP+8] and [EBP+C]you need to know what has been used for.
1. EDI is a pointer to [ebp+8]
2. edx save the pointer of EDI in order to retrieve it whenever edi is changed
3. EAX =0(xor eax,eax => set eax to zero)
4. ecx = -1 (0fffffff =-1)
5. 

