## 对齐
音符的对齐算法是相当复杂的，不但取决于:

* stem类型（stem个数与朝向决定）
* notehead类型
* 是否存在休止符以及休止符的类型
* 是否存在附点以及附点的类型
* 是否存在倚音以及倚音的类型
* 是否存在Slur以及Slur的类型
* 是否存在Tie以及Tie的类型
* 是否存在Tuplet以及Tuplet的类型
* 是否存在临时变号以及临时变号的类型
* 该音符是否为beam的一部分
* Beam中插入Clef或Rest
* 是否存在其他技巧符号
* measure的宽度

等等独立事件，还可能依赖于他们之间的组合。有时甚至存在互相依赖的情况（例如Measure的宽度取决于Measure内部的宽度，Measure内部的宽度又取决于Measure的宽度。）
在很多情况下需要同时确定notehead的位置，beam的尺寸和位置，以及其他所有相关符号的尺寸位置。

首先确定通用的排版规则
1. Stem方向
2. Stem高度
  * Tails与Stem高度
3. Rest的位置
4. Beam角度与方向
  * Beam与Stem高度
  * Beam与Stem方向
  * Beam中插入Clef
  * Beam中插入Rest
  * 异向Stem的Beam
5. Beam分离
6. 旋律与Beam
* Accidentals
* Chord
* Unison
* Dots
* Ties
    * 方向
* Slur
* Dynamics
* Grace
* 节奏与间隔
* Tuplets


### 单stem多notehead
notehead的位置计算方式
如果stem在notehead上方
notehead从低到高，在不发生碰撞的情况下放在stem的左侧，否则放在右侧。
当stem在notehead下方时同理。

```lilypond
        #(set-default-paper-size "a4")
        \paper {
            paper-height = 20
        }
        \header {
            tagline = ##f
        }
      \relative c' {
        <c d> \bar "|"
        <c d e> \bar "|"
        <c d e f> \bar "|"
        <c d e f g> \bar "|"
        <c d e f g a> \bar "|"
        <c' d > \bar "|"
        <c d e> \bar "|"
        <c d e f> \bar "|"
        <c d e f g> \bar "|"
        <c d f g> \bar "|"
      }
```
