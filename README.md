# big-o-part-1



## Requirements

1. **Transcribe the code snippets onto paper using pen and pencil; write the reserved keywords including logical operators in red, variable declarations in blue, and the rest in black.**

2. **Analyze each algorithm using Big-O notation.**

### Example:

```java
int n = 10; // O(1)
int i = 0; // O(1)
while (i < n) { // O(n)
    int j = 0; // O(1)
    while (j < n) { // O(n)
        System.out.println("i: " + i + ", j: " + j); // O(1)
        j++; // O(1)
    }
    i++; // O(1)
}


```
- La línea int n = 10; es una asignación y tiene una complejidad de tiempo constante: O(1).

- La inicialización del contador int i = 0; también es una operación de tiempo constante: O(1).

- El bucle externo while (i < n) se ejecuta n veces, por lo que su complejidad es: O(n).

- Dentro del bucle externo, la inicialización del contador int j = 0; y el bucle interno while (j < n) también se ejecutan n veces en cada iteración del bucle externo, lo que resulta en una complejidad total de: O(n * n) = O(n^2).

- La operación System.out.println("i: " + i + ", j: " + j); es una operación de tiempo constante: O(1).

#### Resultado

> O(1) + O(1) + O(n) + O(n^2) + O(1)

> = O(n^2)




3. **Create a fork of this repository and upload the report with a screenshot of each of the exercises done by hand, explaining the result of the analysis.**

>

## Fragments to Analisys

### **Code 1**
```java
for (int i = 0; i < n; i++) {
}
```
### **Code 2**
```java
for (int i = 0; i < n; i++) {
    for (int j = 0; j < m; j++) {
    }
}
```

### **Code 3**
```java
for (int i = 0; i < n; i++) {
    for (int j = i; j < n; j++) {
    }
}
```

### **Code 4**
```java
int index = -1;
for (int i = 0; i < n; i++) {
    if (array[i] == target) {
        index = i;
        break;
    }
}
```

### **Code 5**
```java
int left = 0, right = n - 1, index = -1;
while (left <= right) {
    int mid = left + (right - left) / 2;
    if (array[mid] == target) {
        index = mid;
        break;
    } else if (array[mid] < target) {
        left = mid + 1;
    } else {
        right = mid - 1;
    }
}
```


### **Code 6**
```java
int row = 0, col = matrix[0].length - 1, indexRow = -1, indexCol = -1;
while (row < matrix.length && col >= 0) {
    if (matrix[row][col] == target) {
        indexRow = row;
        indexCol = col;
        break;
    } else if (matrix[row][col] < target) {
        row++;
    } else {
        col--;
    }
}
```


### **Code 7**
```java
void bubbleSort(int[] array) {
    int n = array.length;
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (array[j] > array[j + 1]) {
                int temp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = temp;
            }
        }
    }
}
```


### **Code 8**
```java
void selectionSort(int[] array) {
    int n = array.length;
    for (int i = 0; i < n - 1; i++) {
        int minIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (array[j] < array[minIndex]) {
                minIndex = j;
            }
        }
        int temp = array[i];
        array[i] = array[minIndex];
        array[minIndex] = temp;
    }
}
```


### **Code 9**
```java
void insertionSort(int[] array) {
    int n = array.length;
    for (int i = 1; i < n; i++) {
        int key = array[i];
        int j = i - 1;
        while (j >= 0 && array[j] > key) {
            array[j + 1] = array[j];
            j--;
        }
        array[j + 1] = key;
    }
}
```

### **Code 10**
```java
void mergeSort(int[] array, int left, int right) {
    if (left < right) {
        int mid = left + (right - left) / 2;
        mergeSort(array, left, mid);
        mergeSort(array, mid + 1, right);
        merge(array, left, mid, right);
    }
}
```

### **Code 11**
```java
void quickSort(int[] array, int low, int high) {
    if (low < high) {
        int pivotIndex = partition(array, low, high);
        quickSort(array, low, pivotIndex - 1);
        quickSort(array, pivotIndex + 1, high);
    }
}
```

### **Code 12**
```java
int fibonacci(int n) {
    if (n <= 1) {
        return n;
    }
    int[] dp = new int[n + 1];
    dp[0] = 0;
    dp[1] = 1;
    for (int i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];
}
```


### **Code 13**
```java
void linearSearch(int[] array, int target) {
    for (int i = 0; i < array.length; i++) {
        if (array[i] == target) {
            // Encontrado
            return;
        }
    }
    // No encontrado
}
```

### **Code 14**
```java
int binarySearch(int[] sortedArray, int target) {
    int left = 0, right = sortedArray.length - 1;
    while (left <= right) {
        int mid = left + (right - left) / 2;
        if (sortedArray[mid] == target) {
            return mid; // Índice del elemento encontrado
        } else if (sortedArray[mid] < target) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return -1; // Elemento no encontrado
}
```

### **Code 15**
```java
int factorial(int n) {
    if (n == 0 || n == 1) {
        return 1;
    }
    return n * factorial(n - 1);
}
```