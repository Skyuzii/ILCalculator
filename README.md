ILCalculator
---
A very simple ILCalculator written in pure IL
```
.assembly extern mscorlib{}
.assembly Calculator{}
.module Calculator.dll
 
.namespace Calculator
{
	.class public abstract sealed auto ansi beforefieldinit Calculator extends [mscorlib]System.Object
	{
	        .method public hidebysig specialname rtspecialname instance void .ctor() cil managed
		{
		  .maxstack 8

		  IL_0000: ldarg.0      
		  IL_0001: call instance void [mscorlib]System.Object::.ctor()
		  IL_0006: nop
		  IL_0007: ret
		}
		
		.method public hidebysig static void Execute() cil managed
		{
			.maxstack 8
			.locals init(
				[0] int32 firstValue,
				[1] int32 secondValue,
				[2] string character,
				[3] int32 result
			)
			
			ldstr "Enter the first number: "
			call void [mscorlib]System.Console::Write(string)
			call string [mscorlib]System.Console::ReadLine()
			call int32 [mscorlib]System.Int32::Parse(string)
			stloc.0
			
			ldstr "Enter the second number: "
			call void [mscorlib]System.Console::Write(string)
			call string [mscorlib]System.Console::ReadLine()
			call int32 [mscorlib]System.Int32::Parse(string)
			stloc.1
			
			ldstr "Enter the character: "
			call void [mscorlib]System.Console::Write(string)
			call string [mscorlib]System.Console::ReadLine()
			stloc.2
			
			ldloc.2
			ldstr "+"
			call bool [mscorlib]System.String::op_Equality(string, string)
			brfalse.s IL_0007
			
			IL_0001: ldloc.0
			IL_0002: ldloc.1
 			IL_0003: add
			IL_0006: call void Calculator.Calculator::WriteResult(int32)
			br IL_0102
			
			IL_0007: ldloc.2
			ldstr "-"
			call bool [mscorlib]System.String::op_Equality(string, string)
			brfalse.s IL_0014 
			
			IL_0008: ldloc.0
			IL_0009: ldloc.1
 			IL_0010: sub
			IL_0013: call void Calculator.Calculator::WriteResult(int32)
			br IL_0102
			
			IL_0014: ldloc.2
			ldstr "*"
			call bool [mscorlib]System.String::op_Equality(string, string)
			brfalse.s IL_0021 
			
			IL_0015: ldloc.0
			IL_0016: ldloc.1
 			IL_0017: mul
			IL_0020: call void Calculator.Calculator::WriteResult(int32)
			br IL_0102
			
			IL_0021: ldloc.2
			ldstr "/"
			call bool [mscorlib]System.String::op_Equality(string, string)
			brfalse.s IL_0100 
			
			IL_0022: ldloc.0
			IL_0023: ldloc.1
 			IL_0024: div
			IL_0027: call void Calculator.Calculator::WriteResult(int32)
			br IL_0102
			
			IL_0100: ldstr "Undefined character"
			IL_0101: call void [mscorlib]System.Console::WriteLine(string)
			IL_0102: ret
		}
		
		.method private hidebysig static void WriteResult(int32 result) cil managed
		{
			IL_0001: ldstr "Result is {0}"
			IL_0002: ldarg.0
			IL_0003: box [mscorlib]System.Int32
			IL_0004: call string [mscorlib]System.String::Format(string, object)
			IL_0005: call void [mscorlib]System.Console::WriteLine(string)
			IL_0006: ret
		}
	}
}
```
