# Lab report 1

## `cd`

1) `cd` with no arguments

```
[user@sahara ~/lecture1]$ pwd
/home/lecture1
[user@sahara ~/lecture1]$ cd
[user@sahara ~]$ pwd
/home
[user@sahara ~]$
```

The working directory when the command was run was `/home/lecture1`.

Because the working directory was not the default home directory `/home`, running `cd` with no arguments changed the directory to the home directory.

This is not an error.

2) `cd` with a directory path as an argument

```
[user@sahara ~]$ cd lecture1/messages
[user@sahara ~/lecture1/messages]$
```

The working directory when the command was run was `/home`.

When ran with a directory path as the argument `cd` changes the working directory to that new directory.

This is not an error.

3) `cd` with a file path as an argument

```
[user@sahara ~/lecture1/messages]$ cd en-us.txt 
bash: cd: en-us.txt: Not a directory
[user@sahara ~/lecture1/messages]$
```

The working directory when the command was run was `/home/lecture1/messages`.

When ran with a file as the argument, `cd` can not change the working directory to that path because it is not a directory.

This is an error because `cd` can not be run with a path to a file as the argument.

## `ls`

1) `ls` with no arguments

```
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$
```

The working directory when the command was run was `/home`.

When ran with no arguments, `ls` lists the contents of the current working directory, which in this case was the directory `lecture1`.

This is not an error.

2) `ls` with a directory path as an argument

```
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
[user@sahara ~]$
```

The working directory when the command was run was `/home`.

When ran with a directory path as an argument, `ls` lists the contents of the directory provided. It does not change the working directory.

This is not an error.

3) `ls` with a file path as an argument

```
[user@sahara ~]$ ls lecture1/Hello.java 
lecture1/Hello.java
[user@sahara ~]$
```

The working directory when the command was run was `/home`.

When ran with a file path as an argument, `ls` only displays the path to that file. That means it outputs the input argument.

This is not an error.

## `cat`

1) `cat` with no arguments

```
[user@sahara ~/lecture1]$ cat
something
something
else
else


^C
[user@sahara ~/lecture1]$
```

The working directory when the command was run was `/home/lecture1`.

When ran with no arguments `cat` accepts user input and displays the same input when enter is pressed.
In this example, the first "something", "else", and "\n" (newline) are all user input and the second occurence is from `cat`.
`^C` (control + c) was used to stop `cat`.

This is not an error.

2) `cat` with a directory path as an argument

```
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
[user@sahara ~/lecture1]$
```

The working directory when the command was run was `/home/lecture1`.

When ran with a directory as an argument `cat` does not work because it can not display the contents of a directory.

This is an error because `cat` does not support running with a directory path.

3) `cat` with a file path as an argument

```
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}[user@sahara ~/lecture1]$
```

The working directory when the command was run was `/home/lecture1`.

When ran with a file path as an argument, `cat` concatenates the contents of the file to the terminal output. In this case, it displays the contents of Hello.java.

This is not an error.
