## 1. Notehead类型
* 常规Notehead {#normal-notehead}
    * 二分音符
    * 四分音符 ... 128分音符
  * 泛音等特殊Notehead

    放在技巧部分

## 宽体Notehead {#wide-body-notehead}
  * 八全音符
  * 四全音符
  * 二全音符

为了一致性，不使用巴洛克风格(左)和双线风格(右侧)的二全音符

```lilypond
    #(set-default-paper-size "a8")
    \paper {
        paper-height = 20
    }
    \header {
        tagline = ##f
    }
            
    \relative c'' {
    \new Staff <<
      \time 4/2
      c\breve
      \override Staff.NoteHead.style = #'baroque
      >>
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
    \new Staff <<
      \time 4/2
      c\breve
      \override Staff.NoteHead.style = #'altdefault
      >>
    }
```
仅使用单线风格的二全音符
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \new Staff <<
          \time 8/1
          c''\breve
        >>
```

  * 全音符

```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
        \new Staff <<
          c''1
        >>
```

## 2. 具体实现

### 2.1 二分音符

```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
    \relative c'' {
      c2
    }
```

### 2.2 四分音符 ... 128分音符

```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
            
    \relative c'' {
      c4 c8 c16 c32 c64 c128
    }
```
