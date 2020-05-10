# Notehead
* 常规Notehead
  * 二分音符

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

  * 四分音符...128分音符

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
  * 泛音等特殊Notehead
    放在技巧部分
* 宽尺寸Notehead
  * 八全音符
  * 四全音符
  * 二全音符
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
为了一致性，不使用巴洛克风格和双线风格的二全音符
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

## 对齐

# Stem

