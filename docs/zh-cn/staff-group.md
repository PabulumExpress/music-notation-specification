# Staff Group
```lilypond
        #(set-default-paper-size "a4")
        \paper {
            paper-height = 300
        }
        \header {
            tagline = ##f
        }
<<
  \new Staff { c'2 c' | c'2 c' }
  \new StaffGroup <<
    \new Staff { g'2 g' | g'2 g' }
    \new StaffGroup \with {
      systemStartDelimiter = #'SystemStartSquare
    }
    <<
      \new Staff { e'2 e' | e'2 e' }
      \new Staff { c'2 c' | c'2 c' }
    >>
  >>

    \new Staff <<
            {c'2 c' | c'2 c'}
        >>
  \new PianoStaff
  <<
    \new Staff { d'1 R1 R1 }
    \new Staff { R1 e'1 R1 }
  >>
>>
<<
  \new Staff { c'2 c' | c'2 c' }
  \new StaffGroup <<
    \new Staff { g'2 g' | g'2 g' }
    \new StaffGroup \with {
      systemStartDelimiter = #'SystemStartSquare
    }
    <<
      \new Staff { e'2 e' | e'2 e' }
      \new Staff { c'2 c' | c'2 c' }
    >>
  >>

    \new Staff <<
            {c'2 c' | c'2 c'}
        >>
  \new PianoStaff
  <<
    \new Staff { d'1 R1 R1 }
    \new Staff { R1 e'1 R1 }
  >>
>>

```

## 定义
StaffGroup由多个通过Staff左侧的边缘延长线连接的Staff组成。


## 装饰
可选的装饰及约定
* 花括号
    * 被装饰的Staff之间的Bar需要延长并连通（见上图）
* 卷花括号
    * 被装饰的Staff之间的Bar需要延长并连通（见上图）
    * 使用多个Staff的乐器需要使用卷花括号，例如键盘乐器
* 方括号
* 无装饰

## 嵌套
* 在StaffGroup中可以划分出子StaffGroup
* 花括号装饰的StaffGroup不能包含方括号装饰的StaffGroup
* 卷花括号装饰的StaffGroup不能被其他括号装饰的StaffGroup包含
* 至多二级嵌套

## 命名
* 关于Staff的命名放在Staff的左侧，文本的上方朝上
* 关于一级嵌套的StaffGroup的命名放在Staff命名的左侧，文本的上方朝左，并关于StaffGroup垂直居中
* 二级嵌套无命名，避免产生歧义
* 命名规则
    * 完整的乐器名称（单数或复数）或缩写加上罗马数字作为编号（可选）
    * 如果StaffGroup的结构不会发生变化，在随后的StaffGroup中可不为其Staff或StaffGroup命名
