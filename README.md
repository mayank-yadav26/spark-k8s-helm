# spark-k8s-helm
This project to learn spark setup on Argo , using k8s and helm charts

i18n means : Internationalization , here 18 are the count of letters between i and n.

**ArrayDeque** is the better choice for a stack or deque in terms of speed and memory efficiency. Use **LinkedList** only if your application requires frequent middle-element operations or modifications, which is uncommon for stacks and deques.

### **. Use Alt + \` (Backtick)**

By default, you can use:

- `Alt + Tab` to switch between different applications.

- `Alt + `\` (backtick, the key above Tab) to switch between windows of the same application.

### **How to Remember**

1. **Order of Arguments**:

    - `Integer.compare(this.freq, other.freq)` → Ascending.

    - `Integer.compare(other.freq, this.freq)` → Descending.

2. **Think "smaller goes first"**:

    - When `this.freq` is compared first, smaller values naturally come first in the sorted order (ascending).

```
Comparator<Pair> comparator = (a,b) -> a.freq==b.freq ? Integer.compare(b.key,a.key)
                             : Integer.compare(a.freq,b.freq);
```

```java
class Pair implements Comparable<Pair>{
        int key;
        int freq;

        public int compareTo(Pair other){
            if(other.freq==this.freq){
                return Integer.compare(other.key,this.key);
            }else{
                return Integer.compare(this.freq,other.freq);
            }
        }
    }
```

```java
HashSet<Character> vowels = new HashSet<>();
Collections.addAll(vowels, 'a', 'e', 'i', 'o', 'u');
```

```bash
# Find string in files
grep -rn "input string" filepath or . for current folder
# -r recursively search in every file
# n  number of line
```

---

### How to Remember:

Think of the mapping as **outside (host)** → **inside (container)**:

1. Host is the external world; Container is the internal environment.

2. The order follows the direction of traffic:

    - Traffic comes from **host (external)** to **container (internal)**.

You can also remember it as:

- **H**ost comes **B**efore **C**ontainer in the alphabet, so `host:container`.



```bash
# Without -n (newline included)
echo "root" | base64
cm9vdAo=

# With -n (no newline)
echo -n "root" | base64
cm9vdA==
```


