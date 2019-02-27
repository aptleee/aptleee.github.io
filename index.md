## DFA

# Construct a DFA

```
  R, m := 256, len(p)
	dfa := make([][]int, R) 
	for i := 0; i < R; i++ {
		dfa[i] = make([]int, m)
	}

	dfa[p[0]][0] = 1
	for x, j := 0, 1; j < m; j++ { 
		for c := 0; c < R; c++ {
			dfa[c][j] = dfa[c][x]
		}
		fmt.Println("x == ", x)
		dfa[p[j]][j] = j+1
		x = dfa[p[j]][x]

	}
```

### what does x = dfa[p[j]][x] mean?
x is the restart state, and x start to increament when there is a character in the pattern that is the same as the first character in pattern




