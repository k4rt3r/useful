# How to rename solutions and projects in Visual Studio

1. Don't.

# How to rename solutions and projects that were created in Visual Studio

1. Close Visual Studio and don't open it again until I tell you. Visual Studio is not competent at renaming things.
2. Assuming you're using git, clean the working folder to remove anything that's not in version control (this will help the search-and-replace step because it won't have to go through a bunch of generated files)
  
    `git clean -fdx`

2. Rename the **solution file** (`.sln`), the project **folders**, and the **project files** (`.csproj`, `.fsproj`)
3. Open the project folder in any good text editor.
4. Search-and-replace across the whole folder and replace and text occurrences of the old name with the new name. Sublime Text and Atom have a tree view where you can right click -> Search in folder. Notepad++ has a "Find in files" option.
5. Hunt around for any weirdly mis-spelt versions of the old name that may not have been caught by the search-and-replace.
6. Specifically, look for a **package.nuspec** (Nuget package manifest) and check the package name in there. It should probably be the same as the solution.
7. (Finally) Open VS again and see if the project loads.
8. See if it builds.
9. Commit and push everything.
9. Don't forget to update any corresponding servcies and integrations, such as:
    * Github repositories
    * Continuous Integration configs
    
    
Credits:

# Update 2020-09-04
ModernRonin has written an automated tool for doing this - give it a go before trying the manual steps here, and let us know how it goes!
https://github.com/ModernRonin/ProjectRenamer
https://www.nuget.org/packages/ModernRonin.ProjectRenamer/
