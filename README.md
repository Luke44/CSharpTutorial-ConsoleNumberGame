# CSharpTutorial-ConsoleNumberGame
I made this by following along to quill18creates' C# tutorial, September 2016.

Aus 01:30 AM, 17/09/2016
I've just signed up and this is my first time using github.
This is the only way I can genuinely see to display my code anywhere on here.
I welcome anyone's input on how to use this website.

C# Console Text Game made with MonoDevelop.
This is for you, quill18.

//============================================================================

using System;

namespace CSharpTutorial {
	
	class MainClass {

		public static void Main (string[] args) {
			Console.WriteLine("Greetings!");
			Console.WriteLine("What's your name?");
			string name = Console.ReadLine();
			Console.WriteLine("Very well then, " + name + "!");
			Console.WriteLine("");
			Console.WriteLine("We are going to play a game.");
			Console.WriteLine("");
			Console.WriteLine("I am thinking of a number from 1 to a");
			Console.WriteLine("million and you must to guess it correctly.");
			Console.WriteLine("");

			Random random = new Random();

			int answer = random.Next(1, 1000001);
			int guess = 0;
			int guessAttempt = 0;

			while (guess != answer) {
				while (guess != answer) {
					guessAttempt++;
					Console.WriteLine("Guess number " + guessAttempt + "!");
					string guessString = Console.ReadLine();

					try {
						guess = int.Parse(guessString);
					} catch (Exception) {
						Console.WriteLine("That is not a number!");
						Console.WriteLine("Guess again!");
						break;
					}

					if (guess == answer) {
						Console.WriteLine("");
						Console.WriteLine("You are correct! Well done!");
						Console.WriteLine("I did not expect that at all!");
					}

					if (guess < answer) {
						Console.WriteLine("Too low!");
						Console.WriteLine("");
					} else if (guess > answer) {
						Console.WriteLine("Too high!");
						Console.WriteLine("");
					}
				}
			}

			Console.WriteLine("Press Enter to dismiss me!");
			Console.ReadLine();
		}

	}

}

//============================================================================
