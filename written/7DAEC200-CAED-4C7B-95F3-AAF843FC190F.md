---
share: true
dg-publish: true
---
  AppleScript | Drafts Script Reference   

Search 

*   Preparing search index...
*   The search index is not available

[Drafts Script Reference](../root/index.html)

[Options](#)

All

*   Public
*   Public/Protected
*   All

 Inherited  Only exported

[Menu](#)

*   [Globals](../globals.html)
*   [AppleScript](applescript.html)

# Class AppleScript

[

# AppleScript

](#applescript)

_**macOS only**. Requires Drafts 19 or greater._

AppleScript objects can be used to execute AppleScripts. It is highly recommended AppleScripts be developed and tested in Apple's Script Editor or similar AppleScript editor, and loaded in Drafts when completed.

[

### Example

](#example)

    // create a local file in App documents
    let method = "execute";
    let script = `on execute(bodyHTML)
        tell application "Safari"
            activate
        end tell
        return "Yeah!"
    end execute`;
    
    let html = draft.processTemplate("<a href="actionlog.html#draft">draft</a>
    ");
    
    let runner = AppleScript.create(script);
    if (runner.execute(method, [html])) {
        // the AppleScript ran without error
        // if the script returned a result, it's available...
        alert(runner.lastResult);
    }
    else {
        alert(runner.lastError);
    }
    

**Note:** When executed, AppleScripts are saved to temporary files in the Drafts' script directory at `~/Library/Application Scripts/com.agiletortoise.Drafts-OSX` and run. The first time a script is executed, the user will be asked to grant permissions to the script directory.

### Hierarchy

*   AppleScript

## Index

### Constructors

*   [constructor](applescript.html#constructor)

### Properties

*   [lastError](applescript.html#lasterror)
*   [lastResult](applescript.html#lastresult)

### Methods

*   [execute](applescript.html#execute)
*   [create](applescript.html#create)

## Constructors

### constructor

*   new AppleScript(script: string): [AppleScript](applescript.html)

*   *   Defined in [AppleScript.d.ts:50](https://github.com/agiletortoise/drafts-script-reference/blob/bb281e8/src/AppleScript.d.ts#L50)
    
    Create new instance.
    
    #### Parameters
    
    *   ##### script: string
        
    
    #### Returns [AppleScript](applescript.html)
    

## Properties

### Optional lastError

lastError: string | undefined

*   Defined in [AppleScript.d.ts:39](https://github.com/agiletortoise/drafts-script-reference/blob/bb281e8/src/AppleScript.d.ts#L39)

If a function fails, this property will contain the last error as a string message, otherwise it will be `undefined`.

### Optional lastResult

lastResult: object | undefined

*   Defined in [AppleScript.d.ts:44](https://github.com/agiletortoise/drafts-script-reference/blob/bb281e8/src/AppleScript.d.ts#L44)

If a the AppleScript subroutine called returns a value and it can be converted to a JavaScript object, it will be stored here. Most basic data types (string, date, numbers), as well as list and records containing those data types, can be returned.

## Methods

### execute

*   execute(subroutine: string, arguments: object\[\]): boolean

*   *   Defined in [AppleScript.d.ts:63](https://github.com/agiletortoise/drafts-script-reference/blob/bb281e8/src/AppleScript.d.ts#L63)
    
    Compiles and executes the AppleScript code, calling the subroutine passed with the arguments.
    
    #### Parameters
    
    *   ##### subroutine: string
        
        The name of a subroutine in the AppleScript to call. [Subroutines](http://www.macosxautomation.com/applescript/sbrt/) are defined using `on subroutineName()` syntax in the AppleScript.
        
    *   ##### arguments: object\[\]
        
        An array of arguments to pass to the subroutine. Most basic Javascript data types, and objects and arrays of those data types, can be passed and will be translated to the proper AppleScript types.
        
    
    #### Returns boolean
    
    `true` if the AppleScript was compiled and executed without error, `false` if not. If `false`, the `lastError` property will contain details regarding the error.
    

### Static create

*   create(script: string): [AppleScript](applescript.html)

*   *   Defined in [AppleScript.d.ts:50](https://github.com/agiletortoise/drafts-script-reference/blob/bb281e8/src/AppleScript.d.ts#L50)
    
    Convenience method to create an AppleScript object.
    
    #### Parameters
    
    *   ##### script: string
        
        A string containing the AppleScript code. This code will be compiled and executed when the `execute` function is called.
        
    
    #### Returns [AppleScript](applescript.html)
    

*   [_Globals_](../globals.html)

*   [AppleScript](applescript.html)
    *   [constructor](applescript.html#constructor)
    *   [lastError](applescript.html#lasterror)
    *   [lastResult](applescript.html#lastresult)
    *   [execute](applescript.html#execute)
    *   [create](applescript.html#create)

## Legend

*   Constructor
*   Property
*   Method

*   Property

*   Static method

Generated using [TypeDoc](https://typedoc.org/)