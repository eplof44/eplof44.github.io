---
layout: post
title:  "Programming Tic Tac Toe With AI"
date:   2017-08-08 13:50:48 +0000
---


After about 6 screen shares with the wonderful technical coaches here and one long night of swearing my future children will never learn to play the game, I have finally finished my ‘Tic Tac Toe with AI’ lab and it feels good.

Most of the lab went pretty smoothly for me (with the exception of my 'turn' method), as I was able to use some of the conceptual ideas from the Intro to Ruby course. However, I hit a road block when I was trying to get my computer AI to play with some type of strategy. I really wanted to create block or win methods that would make the computer take the unoccupied spot that would make it win or block.

Unfortunely, nothing was working out for me in constructing those methods, so I decided to start a bit simpler. Eventually, I was able to create methods that told the computer to:

Go in the middle if middle is available:

```
  def move(board)
      if !board.taken?("5")
        "5"
      elsif !take_corner(board).empty?
       take_corner(board).sample
     else random(board)
      end
    end

```

Go in a corner if the corner is available:

```
 def take_corner(board)
      corners = ["1","3","7","9"]
      corners.select { |move| !board.taken?(move)}
    end

```

Then, take random spot:

```

    def random(board)
      move = (1..9).to_a
      move.sample.to_s
    end
```


In another, more advanced, universe, I would like to create those block or win methods. This is a lab I would like to go back to as I continue through the course and enhance the AI portion. For now, I have to remember that I’ve only been programming Ruby for about two months now and have to give myself some credit. 
