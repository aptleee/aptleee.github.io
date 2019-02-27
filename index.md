## DFA

Construct a DFA

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


### what does X mean?

