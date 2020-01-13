# TODO

- [X] Define the schema
    + [X] empty schema should raise an error
    + [X] non array schema should raise an error
    + [X] if nothing is passed in place of the schema should throw error
    + [X] pass flag name, type (Bool, string, integer), and default value.
        * [X] schema should inform name
        * [X] schema should inform type
        * [X] schema should inform default
    + [X] test schema fields?
    + [X] should return the schema default for not informed arguments

## Schema
- [X] try and get an argument that's not on the schema.
- [X] Validate missing default value considering arg type
- [X] Empty string is a valid value for the "default" schema field
- [X] Parse default value to target type

## Parsing
- [X] should parse an array of strings
    + [X] array with a value that differs from the default
    + [X] empty arrays are valid.
- [X] flags should be one character, preceeded by a minus sign
- [X] arguments that are not in the schema should raise error explaining the situation
- [X] the program can ask for the flag using it's name. "nameof -p -> p"
- [X] input will be an array of string. ``
- [] handle if input parameter has empty spaces
- [-] ~check for invalid extra space btw flags~ -> out of scope

- [X] should throw an exception if the same flag is passed more than once.

- [X] for boolean flags it should return true if it's defined on the args.
- [X] validate input "-d -d"

- [X] Validate input value types with the schema (ex.: "-l mariola" should throw an error)
- 
### For NExt Session

- [] Throw an error if there is a string argument without value

- [] what happens if the user tries to parse a flag with more than one letter? e.g. -FakeFlag
- [] check if we can enhance the argsParse._parseValue

## Examples
- `-l -p 8080 -d /usr/logs -> ["-l","-p","8080","-d","/usr/logs"]`
- `-l -p 8080 -n `

- Given: schema = [{name: 'l', type: 'bool', default: 'true'}]
         inputArgs = ["-l"]
- When: parser.Parse(inputArgs);
- Then: parser.getValue === true;

- Given: schema = [{name: 'l', type: 'bool', default: 'true'}]
         inputArgs = ["-l", "false"]
- When: parser.Parse(inputArgs);
- Then: parser.getValue === false;