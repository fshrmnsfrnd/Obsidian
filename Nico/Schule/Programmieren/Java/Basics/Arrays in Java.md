---
Fach: "[[Programmieren]]"
tags:
Thema:
  - "[[Java]]"
---
# Declare
---
```java
int[] a1;
int[] a2 = {1, 2, 3};
int[] a3 = new int[]{1, 2, 3};

int[] a4 = new int[3];
a4[0] = 1;
a4[2] = 2;
a4[3] = 3;
```

# Multidimensional
---
```java
int[][] matrix = { {1, 2, 3}, {4, 5} };

int x = matrix[1][0];  // 4
// [[1, 2, 3], [4, 5]]
Arrays.deepToString(matrix)

for (int i = 0; i < a.length; ++i) {
	for(int j = 0; j < a[i].length; ++j) {
		System.out.println(a[i][j]);
	}
}
// Outputs: 1 2 3 4 5 6 7 

```

# Methoden
---
```java
char[] chars = {'b', 'a', 'c'};
Arrays.sort(chars);
Arrays.toString(chars);
```