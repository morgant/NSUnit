NSUnit (NewtonScriptUnit)
=========================

by Morgan Aldridge <morgant@makkintosshu.com>

OVERVIEW
--------

NSUnit is a basic [xUnit](http://en.wikipedia.org/wiki/XUnit) unit testing framework for the NewtonScript language, based on the following implementations:

* [Simple Smalltalk Testing: With Patterns](http://www.xprogramming.com/testfram.htm) by Kent Beck
* [JUnit](http://junit.sourceforge.net/)
* [PHPUnit](http://www.phpunit.de/manual/current/en/index.html)

It is currently being developed with [NEWT/0](http://gnue.github.com/NEWT0/), but the eventual goal is to support both NEWT/0 and native NewtonOS use. It is an exercise in NewtonScript development for me, but should aid in general NewtonScript development as the general debugging tools are somewhat lacking.

THIS IS STILL IN DEVELOPMENT AND IS NOT FULLY FUNCTIONAL OR STABLE.

USAGE
-----

	// If using NEWT/0
	Require("NSUnit");
	
	NSUnit := GetGlobalVar('|NSUnit:makkintosshu|);
	
	// Build out a test suite
	myTestSuite := {
		_proto: NSUnit.protoNSUnitTestSuite,
		// Create one or more test cases
		testCases: [
			{
				_proto: NSUnit.protoNSUnitTestCase,
				// Create any number of methods that start with the word "Test"
				TestSomethingNil: func () begin
						// do whatever you need to do, calling various Assert*() methods provided by NSUnit
						self:AssertNil(nil);
					end
			}
		]
	};
	
	// Run all the tests in the test suite
	myTestSuite:Run();

LICENSE
-------

Copyright (c) 2012, Morgan T. Aldridge
All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
