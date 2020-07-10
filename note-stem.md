## 1. stem类型
### 同向非对齐嵌入型双stem
将右上角两个音符或者左下角两个音符视为一组(尽管从理论上他们四个是一组的)，他们的stem是同向的非垂直对齐的
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \new Staff <<
          { f''2 }  % 1: highest
          \\
          { c'2 }  % 2: lowest
          \\
          { d''2 }  % 3: second-highest
          \\
          { e'2 }  % 4: second-lowest
        >>
```
### 同向非对齐非嵌入型双stem
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \new Staff <<
          { d''2 }  % 1: highest
          \\
          { c'2 }  % 2: lowest
          \\
          { e''2 }  % 3: second-highest
          \\
          { d'2 }  % 4: second-lowest
        >>
```
### 异向对齐双stem
它们的Notehead垂直对齐
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \new Staff <<
          { f' }
          \\
          { c'8 }
        >>
```
### 异向对齐共享型双stem
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \new Staff <<
          { f' }
          \\
          { f'8 }
        >>
```
### 异向非对齐嵌入型双stem(A型)
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \relative c' {
          <<
          {c8}
          \\
          {e}
          >> \bar "|"
        }
```
### 异向非对齐嵌入型双stem(B型)
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \relative c' {
          <<
          {c8}
          \\
          {d}
          >> \bar "|"
        }
```

### 异向非对齐非嵌入型双stem
TODO stem组的方向 或者 stem组的左右位置的计算规则
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \relative c' {
          <<
          {c'8}
          \\
          {<e c>}
          >> \bar "|"
        }
```
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \relative c'' {
          <<
          {<c e>8}
          \\
          {<b f>16}
          >> \bar "|"
        }
```
