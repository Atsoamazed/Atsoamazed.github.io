---
layout: post
title:      "Introduction to Ruby"
date:       2017-12-24 16:32:08 +0000
permalink:  introduction_to_ruby
---


My first month of coding, went a lot different then I had planed. Getting started with Ruby was alot harder then I thought. I never finished the Ruby section on the bootcamp prep. I choose to focus my prep on Javascript/HTML/CSS. 

This was my first time even seeing Ruby code. I wish I started with Ruby as the first lanagauge because the syntax is very simple and easy to read. I utizilied a few study groups and  tried to help answer any questions, whenever possiable as it helps with my learning process. The Introduction to Ruby section took me  longer then I had anticpated about 6 weeks to complete as I went away on holiday for about a week and then life happened. Then I got stuck on the Classes , interalization and procedural to Object Oreintation lab. Finally completing  section 1 Intro to Ruby section. I understand why Ruby is considered  the langauge to make programmers happy. =) 


Some helpful tools that help me complete the first section here include the following books:

* Complete Ruby for the Abosolute Beginners Jerry Lee Ford JR. 
* Beginning Ruby  From Novice to Professionals Peter Cooper
* The Ruby Programming Langague David Flanagan & Yukihiro Matsumoto
* Computer Science Programming Basics in Ruby Ophir Frieder
* Learning Ruby Michael Fitzgergerald 

Some helpful online resources: 
CodeAcademey Learn Ruby
https://www.codecademy.com/learn/learn-ruby

Tutorials points 
https://www.tutorialspoint.com/ruby/ruby_overview.htm


Helpful Github respirtories 
https://github.com/ruby/ruby/tree/trunk/doc/syntax



Here is my OO Tic Tac Toe  code:
```
class TicTacToe
  WIN_COMBINATIONS = [[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]]

  def initialize (board = nil)
    @board = board || Array.new(9, " ")
  end
  def display_board
      puts " #{@board[0]} | #{@board[1]} | #{@board[2]} "
      puts "-----------"
      puts " #{@board[3]} | #{@board[4]} | #{@board[5]} "
      puts "-----------"
      puts " #{@board[6]} | #{@board[7]} | #{@board[8]} "
    end

    def input_to_index(user_input)
      user_input.to_i - 1
    end

    def move(input_to_index, character)
      @board[input_to_index] = character
    end

    def position_taken?(index)
    if @board[index]== "X" || @board[index] == "O"
      true
    else
      false
    end
    end

    def valid_move?(index)
    if !position_taken?(index) && index.between?(0, 8)
      return true
    else
    return false
    end
    end

    def turn
      @board
      puts "Please enter 1-9:"
      user_input = gets.strip
      index = input_to_index(user_input)
    if valid_move?(index)
      move(index, current_player)
     display_board()
    else
      puts "Sorry, that was incorrect, please enter 1-9:"
    turn()
    end
    end

    def turn_count
      @board.count{|token| token == "X" || token == "O"}
    end

    def current_player
  turn_count % 2 == 0 ? "X" : "O"
    end


  # part two working on the won instance method

def won?
  WIN_COMBINATIONS.detect do |win_combination|
   @board[win_combination[0]] == @board[win_combination[1]] && @board[win_combination[1]] == @board[win_combination[2]] && position_taken?(win_combination[0])
     end
  end

  def full?
  @board.all? { |index| index == "X" || index == "O"}
  end


  def draw?
  if !won? && full? == true
    return true
  else
    return false
  end
  end

  def over?
  if won?
    return true
  elsif draw?
    return true
  else
    return false
  end
  end

  def winner
   if win = won?
     return  @board[win[0]]
   end
   end

   def play
   while !over?
 turn
 end
   if won?
       puts "Congratulations #{winner}!"
     elsif draw?
         puts "Cat's Game!"
   end
   end
end

```


I am excited to continue my learning process and move onto the next section Git/Github


