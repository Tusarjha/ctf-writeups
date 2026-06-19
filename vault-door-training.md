# vault-door-training - Writeup

## Challenge

A Java source file `VaultDoorTraining.java` was provided. The goal was to determine the correct vault password.

## Analysis

Downloaded and viewed the source code:

```bash
wget <challenge-url>
cat VaultDoorTraining.java
```

Inspecting the code revealed the password verification function:

```java
public boolean checkPassword(String password) {
    return password.equals("w4rm1ng_Up_w1tH_jAv4_000AXPNPN0i");
}
```

The password was hardcoded directly inside the source code.

The program also extracted the contents inside the picoCTF flag format:

```java
String input = userInput.substring("picoCTF{".length(),
                                   userInput.length()-1);
```

Therefore the required flag format was:

```text
picoCTF{password}
```

## Flag

```text
picoCTF{w4rm1ng_Up_w1tH_jAv4_000AXPNPN0i}
```

## Concepts Learned

* Reverse Engineering Basics
* Reading Java source code
* Understanding password validation logic
* Extracting hardcoded secrets from source code

## Key Takeaway

If source code is available, sensitive information such as passwords should never be hardcoded, because anyone can read the code and recover the secret.
