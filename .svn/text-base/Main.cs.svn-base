/*
 * Created by SharpDevelop.
 * User: novalis78
 * Date: 05.12.2004
 * Time: 15:19
 * 
 * To change this template use Tools | Options | Coding | Edit Standard Headers.
 */
using System;
using PreludeEngine;

namespace pleTest
{
	class MainClass
	{
		private static string ind = "";
		public  static PreLudeInterface pi;
		
		public static void Main(string[] args)
		{
			Console.WriteLine("Prelude@# (0.5.0) command line version, welcome user!");
			Console.WriteLine("if you want to stop chatting, enter: 'exit'");
			//initialize interface
			pi = new PreLudeInterface();
			//auto speak handler (if bored...)
			pi.reportBoredom += new PreLudeInterface.AutoSpeakHandler(iamBored);
			//define path to mind file
			pi.loadedMind = "mind.mdu";			
			//start your engine ...
			pi.initializeEngine();
			//here we go:
			while(!ind.StartsWith("exit"))
			{
				Console.Write("You say: ");
				ind = Console.ReadLine();
				Console.WriteLine("Prelude says: " + pi.chatWithPrelude(ind));
			}
			pi.stopPreludeEngine();
		}
		
		private static void iamBored(string a)
		{
			Console.WriteLine("\n" + "Prelude to herself: " + a);
			Console.WriteLine("Prelude bored: " + pi.chatWithPrelude(a));
		}
	}
}
