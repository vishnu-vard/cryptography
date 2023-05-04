def gcd(a, b):
    """
    Returns the greatest common divisor of two numbers a and b.
    """
    if b == 0:
        return a
    else:
        return gcd(b, a % b)

def is_coprime(a, b):
    """
    Returns True if a and b are coprime, False otherwise.
    """
    return gcd(a, b) == 1

def is_valid_affine(a, b):
    """
    Returns True if the values of a and b satisfy the conditions for a valid affine cipher,
    i.e. a is coprime with 26 and b is between 0 and 25.
    """
    return is_coprime(a, 26) and b >= 0 and b < 26

def encrypt_affine(msg, a, b):
    """
    Encrypts a message using the affine cipher with the given values of a and b.
    """
    ciphertext = ''
    for c in msg:
        if c.isalpha():
            # Convert the letter to its corresponding index in the alphabet
            # (A -> 0, B -> 1, ..., Z -> 25)
            idx = ord(c.upper()) - ord('A')
            # Apply the affine transformation
            idx = (a * idx + b) % 26
            # Convert the index back to its corresponding letter
            ciphertext += chr(idx + ord('A'))
        else:
            ciphertext += c
    return ciphertext

# Testing the program
msg = "HELLO WORLD"
a = 5
b = 7
if is_valid_affine(a, b):
    ciphertext = encrypt_affine(msg, a, b)
    print("plaintext:", msg)
    print("Ciphertext:", ciphertext)
else:
    print("Invalid values of a and/or b.")
