# EX-NO14-HASH-ALGORITHM

## AIM:
To implement HASH ALGORITHM

## ALGORITHM:

1. Hash Algorithm is used to convert input data (message) into a fixed-size string, typically a hash value, which uniquely represents the original data.

2. Initialization:
   - Choose a hash function \( H \) (e.g., SHA-256, MD5, etc.).
   - The message \( M \) to be hashed is input.

3. Message Preprocessing:
   - Break the message \( M \) into fixed-size blocks. If necessary, pad the message to make it compatible with the block size required by the hash function.
   - For example, in SHA-256, the message is padded to ensure that its length is a multiple of 512 bits.

4. Hash Calculation:
   - Process the message block by block, applying the hash function \( H \) iteratively to produce an intermediate hash value.
   - For SHA-256, each block is processed through a series of logical operations, bitwise manipulations, and modular additions.

5. Output:
   - After all blocks are processed, the final hash value (digest) is produced, which is a fixed-size output (e.g., 256-bit for SHA-256).
   - The resulting hash is unique to the input message, meaning even a small change in the message will result in a completely different hash.

6. Security: The strength of the hash algorithm lies in its collision resistance, ensuring that it is computationally infeasible to find two different messages that produce the same hash value.


## Program:
```
def compute_simple_hash(message: str) -> int:
    temp = 0
    for char in message:
        temp ^= ord(char)   
        temp += ord(char) 
    return temp & 0xFF 

def main():
    message = input("Enter the message: ")
    hash_value = compute_simple_hash(message)
    print(f"Computed Hash (in hex): {hash_value:02x}")
    received_hash_hex = input("Enter the received hash (in hex): ").strip()
    try:
        received_hash_value = int(received_hash_hex, 16)
    except ValueError:
        print("Invalid hexadecimal input.")
        return
    if hash_value == received_hash_value:
        print("Hash verification successful. Message is unchanged.")
    else:
        print("Hash verification failed. Message has been altered.")

if __name__ == "__main__":
    main()

```

## Output:
![image](https://github.com/user-attachments/assets/37cb785d-5863-4597-b36b-2edb9ccb23fe)

## Result:
The program is executed successfully.
