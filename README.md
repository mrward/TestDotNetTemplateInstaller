# TestDotNetTemplateInstaller

This is a console app that uses the [.NET Templating engine](http://github.com/dotnet/templating) and tries to use
the IDE installer to install from a directory. Running this console app results in the TestDotNetTemplateInstaller
project and all files being deleted. The templating engine finds some .dll files in a subdirectory and then proceeds
to delete all the files and the project directory. The [TemplateCache](https://github.com/dotnet/templating/blob/bfc767e526213c069efacf88f676ececb3db2070/src/Microsoft.TemplateEngine.Edge/Settings/TemplateCache.cs#L264)
causes the deletion. Not expecting this to happen when using a file system mount point. The template cache should
not delete any files if a folder is being scanned.
