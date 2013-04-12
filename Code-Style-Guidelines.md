This document will define a set of code style guidelines that we would like to use in order to help maintain consistency throughout the Torque 3D codebase.  While some points covered deal strictly with the C++ source code, many of the style principles can be used with the scripts as well.   

## File Architecture

The standard order for the parts of a code file is as follows:
 1. File Header Comment (Always Required)
 2. #includes
 3. #defines
 4. Local structures
 5. Static local variables
 6. Static function prototypes
 7. Static and global functions
 8. Class methods
 9. Console Exposed Class Methods

## File Header Comment
All files must begin with a File Header Comment that contains the copyright and licensing information.  The format for this header is as follows:
```
//-----------------------------------------------------------------------------
// Copyright (c) 2012 GarageGames, LLC
//
// Permission is hereby granted, free of charge, to any person obtaining a copy
// of this software and associated documentation files (the "Software"), to
// deal in the Software without restriction, including without limitation the
// rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
// sell copies of the Software, and to permit persons to whom the Software is
// furnished to do so, subject to the following conditions:
//
// The above copyright notice and this permission notice shall be included in
// all copies or substantial portions of the Software.
//
// THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
// IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
// FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
// AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
// LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
// FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
// IN THE SOFTWARE.
//-----------------------------------------------------------------------------
```

## The #define Guard
To prevent recursive inclusion, all header files (`filename.h`) have an `#ifndef` directive immediately following the File Header Comment, and a corresponding `#endif` directive as the last line of the header file.  The following example shows the proper format and nomenclature for a header file called `BaseClass.h`
```
#ifndef _BASECLASS_H_
#define BASECLASS_H_
 
// rest of header file for baseclass.h

#endif // _BASECLASS_H_
```

## Formatting

### Comments

Use the `// comment` notation rather than the `/* comment */` notation.  The latter style of comment leads to confusion when comments are nested.  Furthermore, since the `/*` and `*/` can span multiple lines, it is difficult to pair up the starting and ending points of the commented code.

### Tabs

You should never use Tab characters in any code file.  Tab spacing is dependent on the application used to view the file and almost always results in misaligned code.  It is your responsibility to ensure that your code editor is not introducing Tabs into the source code.  Tab stops are to be set at 4, 7, 10, etc. (i.e., 1 tab = 3 spaces).  It is your responsibility to ensure your editor is inserting three spaces for each tab stop.

### Brackets and Indentation

Brackets should be matched in the same column. Example:
```
if ( flag )
{
   for ( int i=0; i<10; i++ )
   {
      // some code
   }
   // some code
}
else
{
    // some code
}
```

All indentation aligns itself along one of the tab stops (columns 4, 7, 10, ..., see earlier section on Tabs for details).

Single line statements after a `for`, `if`, or `while` statement must be on their own lines.  It makes it much easier to trace and debug when you can tell if the statement was executed.
```     
if ( obscureCondition == true )  obscureVar += strangeVar; // breakpoint this?

if ( obscureCondition == true )
    ObscureVar += strangeVar;                              // breakpoint here!
```

In general, brackets are not required for single-line statements, but they are allowed if you like them.  However, if one part of an if-else statement uses brackets, the other part must as well.

### Horizontal Whitespace (Spaces)

Some people like to include spaces after an opening parentheses, brace, or bracket, and a space before the pair is closed.  Others do not like this practice.  We will not strictly enforce one preference over another; either is fine, but be consistent. If you are modifying a file, use the format that is already present. If you are writing new code, use the format that the other files in that directory or module use.  

## Variable Declarations

>"The most important consideration in naming a variable is that the name fully and accurately describes the entity the variable represents.  An effective technique is to state in words what the variable represents. Often, that statement itself is the best variable name" (Code Complete, chapter 9, pp 185).

Variables should have one purpose in a program.  Do not use 'i' as an index entry and then use the same variable to calculate the number of stars in the galaxy.

Avoid exposing member variables publicly.  If the class needs to expose the variable’s state then an accessor function should be created. 

Avoid using global variables.  Global variables are too easy to be changed unwittingly by another class and make debugging extremely difficult.  If there truly is a need for global access to the value, a special class should be used to wrap the value and at least give someone debugging an easy way to see when the value is being changed.  These variables should be declared as private members which prevents them from being used without the accessor function. 

Do not use intrinsic types.  All of the variable types have been replaced to allow for cross-platform compiling.
```
Use    Don't use
F32    float
F64    double
S32    int
S16    short
S8     char
U32    unsigned int
U16    unsigned short
```

Global variables are prefixed with lower case g:
```
gConsole->printf();
gManager = NULL;
```

Class member variables of non-data classes are prefixed with lower case m:
```
const char * mObjectName;
S32 mType;

// this is a data class, m prefix not needed
class Point3F
{
   F32 x,y,z;
};
```

Static member variables should be prefixed with lower case sm:
```
static S32 SomeClass::smObjectCount;
```

Use only the prefix characters defined here.  Do not make up your own prefixes to use in addition to these.

All non-constant variables are in [lower CamelCase](http://en.wikipedia.org/wiki/CamelCase) (starts with a lowercase letter and the first letter of all subsequent words in the variable name are capitalized -- `thisIsInLowerCamelCase`).  Do not use underscores `_` to separate words in variable names.  Local variables do not require a prefix but must start with a lower case letter.
```
S32   mMemberVariable;   // good member variable
F32   volumeLevel;       // good local variable
```

All constant variables should be entirely uppercase letters.  Words in the variable are separated by underscores `_`.
```
#define   MAX_FILE_SIZE 256
const S32 MAX_ELEMENT_COUNT = 128;
```

The preferred method of declaring constant variables is to use const declarations.  If `#define` macros are used, a type identifier should accompany the value. This is to prevent ambiguous interpretation of the constant type. Example:
```
#define   MAX_POWER_LEVEL   10.0f
#define   NUM_POWER_LEVELS ((S32) 5)
```

Avoid the use of `#define` macros that perform a function. The preferred method is to create an inline function.

## Function Declarations

Member function names are in lowerCamelCase.
```
void MyClass::myMethodForThisClass()
{
}
```

Non-member functions can be either local or global in scope.  A function that is used only within a given file should be declared as a static function so that it has a local scope.  A function used outside the file should be declared as extern in the header file and should have the first letter of it's name capitalized to distinguish it from local functions.
```
// good name for a global function
Time GetCurrentTime()
{
}

// good name for local (static) localfunction
static Interior & getNextInterior()
{
}
```

## Parting Words

Use common sense and BE CONSISTENT.  If you are modifying code, take a look at the code itself and determine its style.  If code you add to a file looks drastically different from the existing code around it, the discontinuity throws readers off when they go to read it, which makes maintaining it more difficult.  Try to avoid this.