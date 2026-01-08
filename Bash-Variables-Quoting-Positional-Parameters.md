## 📝 Bash Variables, Quoting & Positional Parameters

Bash mein variables, quoting aur positional parameters ko sahi tarah se use karna professional scripting ka core concept hai. Yeh notes aapke Linux learning journey ka ek solid reference ban sakte hain.

---

## 1. Variables: Dabba Banana 🎯

Bash mein variable ek **dabba** jaisa hota hai jisme aap temporary data store karte ho. Syntax strict hai:

```bash
# ✅ Sahi tarika
name="jaysharma"
age=21
status="This is good"

# ❌ Galat tarika (Bash isse command samajh lega)
name = "jaysharma"
```

- `=` ke dono taraf **space nahi** honi chahiye.
- Best practice: variable names ko lowercase + underscore ka use karke likho, jaise `user_name`, `total_count`.

---

## 2. Values Display Karna: Dabba Kholna 📤

Variable ka value dikhane ke liye `echo` ke sath `$variable` use hota hai.

```bash
name="jaysharma"
age=21
status="This is good"

echo "I want to say that ${status} and my age is ${age} and I want to ask you..."
# Output:
# I want to say that This is good and my age is 21 and I want to ask you...
```

- String ke andar multiple variables ko mix karke likhne ke liye `"I am ${name} and I am ${age} years old"` jaisa pattern follow karo.

---

## 3. `$var` vs `"${var}"`: Khula vs Packed 📦

Ye part real‑world scripts mein sabse zyada problems ko prevent karta hai.

| Concept        | Khula: `$file`           | Packed: `"${file}"`          |
|----------------|--------------------------|------------------------------|
| Analogy        | Khule haath mein samaan  | Seal-pack **box**            |
| Spaces         | Space aate hi toot jayega | Spaces safe handle honge     |
| Boundary       | `versionnd` confuse karega | `${version}nd` clear boundary |

**Real-world risk example:**

```bash
file="My Photo.jpg"

rm $file     # ❌ Bash isse 'My' aur 'Photo.jpg' do alag arguments samjhega
rm "$file"   # ✅ Ek hi file delete hogi: "My Photo.jpg"
```

Isliye habit banao: jab bhi variable likho, almost hamesha `"${variable}"` use karo.

---

## 4. Command Substitution: The "Monitor" Rule 🤖

Jab kisi command ka output variable mein store karna ho, wahan command substitution use hota hai.

**Old way (avoid):**

```bash
# ❌ Purana aur messy
num_line=`ls "$HOME" | wc -l`
```

**Modern way (recommended):**

```bash
# ✅ Saaf aur readable
num_line=$(ls "${HOME}" | wc -l)
echo "Files in home: ${num_line}"
```

Analogy:

- `ls "${HOME}"` → Monitor ne class ke bachchon ki list banayi.  
- `| wc -l` → Helper ne count kiya kitne bachche hain.  
- `$( ... )` → Helper ne result ek chhoti parchi pe likh kar diya.  
- `num_line=...` → Aapne woh number apni diary (variable) mein store kar liya.  

---

## 5. Pro Tips for Safe Scripting 💡

- Hamesha quotes lagao: `"${variable}"` use karo, especially jab spaces ka chance ho.
- Boundary fix karo: `${var}nd` jaisa pattern use karo taaki Bash ko pata ho variable ka naam kahan khatam ho raha hai.
- Security first: user input validate karo, jaise sirf numbers ke liye:

```bash
read -p "Enter a number: " input

if [[ ${input} =~ ^[0-9]+$ ]]; then
  echo "Valid number: ${input}"
else
  echo "Invalid input!"
fi
```

---

## 6. User Input: `read -p` 🧾

User se data lene ka standard tareeka `read` hai.

```bash
read -p "Enter your name: " name
echo "Your name is ${name}"
```

- `-p` ke baad jo string hai woh turant terminal par message ki tarah dikhai degi.  
- Uske baad jo user type karega woh given variable (yahan `name`) mein store ho jayega.

---

## 7. Positional Parameters: Delivery Service 🚚

Positional parameters woh **special variables** hain jo script ko terminal se arguments milte hi assign ho jaate hain.

Assume script ka naam hai `order.sh`:

```bash
./order.sh Pizza 2 Coke
```

Yahan Bash in values ko positions par bitha deta hai:

- `$0` → Script ka naam → `./order.sh`  
- `$1` → Pehla argument → `Pizza`  
- `$2` → Dusra argument → `2`  
- `$3` → Teesra argument → `Coke`  

---

## 8. Important Positional Parameters 📋

| Parameter | Kaam                                | Example (./order.sh Pizza 2 Coke) |
|-----------|-------------------------------------|------------------------------------|
| `$0`      | Script file ka naam                | `./order.sh`                       |
| `$1,$2..` | Individual arguments               | `$1 = Pizza`, `$2 = 2`, `$3 = Coke`|
| `$#`      | Total arguments ka count           | `3`                                |
| `$@`      | Saare arguments, **alag‑alag items** | `Pizza`, `2`, `Coke`               |
| `$*`      | Saare arguments ek single string    | `Pizza 2 Coke`                     |

Best practices:

- Zyada tar cases mein `"${@}"` use karna better hota hai kyunki yeh arguments ko individual items ki tarah treat karta hai.
- 9 se aage arguments ke liye `${10}`, `${11}` jaisa syntax use hota hai, isme curly braces required hote hain.

---

## 9. Positional Parameters + Quotes Example

```bash
#!/usr/bin/env bash

echo "Script name: $0"
echo "First item: $1"
echo "Second item: $2"
echo "Total items: $#"

echo "All items (as list): $@"
echo "All items (as one string): $*"
```

- Is script ko `./order.sh Pizza 2 Coke` se run karoge to upar wala mapping bilkul delivery‑service analogy jaisa behave karega.

---

### Day 12 – Bash Variables, Quoting & Positional Parameters

**Learning Outcome**: Professional bash scripting ke liye variables ko safely use karna, quoting se security maintain karna aur positional parameters ke through script arguments handle karna seekh liya.

---

**Author**: jaysharma21-05  
**Repository**: [Linux-Journey](https://github.com/jaysharma21-05/Linux-Journey)  
**Date**: January 2026
