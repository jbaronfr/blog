---
title: "TIL: NuGet supports new csproj not PackageReference"
categories:
  - TIL
tags:
  - NuGet
  - csproj
  - PackageReference
link: https://github.com/NuGet/Home/issues/4491#issuecomment-527152856
---

In a project with the new csproj format and dependencies described with PackageReference, if you want your dependencies properly included in your package use `dotnet pack` instead.

If you are stuck with NuGet, you will have to create a `.nuspec` file and precise `<dependencies>` and `<frameworkAssemblies>`.

**TIPS :** you can use `dotnet pack` to generate a well designed package and then open it with [NuGet Package Explorer](https://www.microsoft.com/store/productId/9WZDNCRDMDM3) 
to retrieve its metadata for your `.nuspec`. For `<version>` use `$version$` if you want your CI/CD to handle it for you.
