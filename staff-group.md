# Staff Group
```lilypond
        #(set-default-paper-size "a8")
        \paper {
            paper-height = 70
        }
        \header {
            tagline = ##f
        }
<<
  \new Staff { c2 c | c2 c }
  \new StaffGroup <<
    \new Staff { g2 g | g2 g }
    \new StaffGroup \with {
      systemStartDelimiter = #'SystemStartSquare
    }
    <<
      \new Staff { e2 e | e2 e }
      \new Staff { c2 c | c2 c }
    >>
  >>

    \new Staff <<
            {c''2}
        >>
>>

```

* 嵌套