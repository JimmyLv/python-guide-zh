# Installing Python on Windows（在Windows上安装Python）

> First, download the latest version of Python 2.7 from the official Website. If you want to be sure you are installing a fully up-to-date version then use the “Windows Installer” link from the home page of the Python.org web site .

首先，从官网下载最新的Python 2.7版本。如果你想确保你安装的是完全最新版本，点击Python.org网站的首页上的“Windows Installer”链接。

> The Windows version is provided as an MSI package. To install it manually, just double-click the file. The MSI package format allows Windows administrators to automate installation with their standard tools.

得到的Window版本是一个MSI包。只需双击文件就可以手动安装它了。这个MSI包格式可以让Windows管理员通过标准工具自动化安装。

> By design, Python installs to a directory with the version number embedded, e.g. Python version 2.7 will install at `C:\Python27\`, so that you can have multiple versions of Python on the same system without conflicts. Of course, only one interpreter can be the default application for Python file types. It also does not automatically modify the `PATH` environment variable, so that you always have control over which copy of Python is run.

Python被设计安装在带有版本号的目录中，例如：Python 2.7将安装在`C:\Python27\`，这样你就可以无冲突得在同一系统安装多个版本的Python。当然，只有一个解释器可以作为Python文件类型的默认应用程序。它也不会自动修改`PATH`环境变量，所以你总是需要控制那个Python副本的运行。

> Typing the full path name for a Python interpreter each time quickly gets tedious, so add the directories for your default Python version to the `PATH`. Assuming that your Python installation is in `C:\Python27\`, add this to your `PATH`:

每次都需要输入整个Python解释器完整路径是非常单调的，所以需要添加你的默认Python版本目录到`PATH`中。假设你的Python安装路径是`C:\Python27\`，添加到`PATH`:

```
C:\Python27\;C:\Python27\Scripts\
```

> You can do this easily by running the following in `powershell`:

你也可以在`powershell`运行以下代码轻松做到：

```
[Environment]::SetEnvironmentVariable("Path", "$env:Path;C:\Python27\;C:\Python27\Scripts\", "User")
```

> The second (`Scripts`) directory receives command files when certain packages are installed, so it is a very useful addition.

但某些包被安装的时候第二个`Scripts`目录会接受命令文件，所以添加这个路径是非常有用的。

> You do not need to install or configure anything else to use Python. Having said that, I would strongly recommend that you install the tools and libraries described in the next section before you start building Python applications for real-world use. In particular, you should always install `Setuptools`, as it makes it much easier for you to use other third-party Python libraries.

你不需要安装和配置任何东西就可以使用Python，话虽如此，在你开始构建实际使用的Python程序之前，我强烈建议你安装在下一节中描述的工具和库。特别的是，你最应该安装`Setuptools`，因为它可以让你非常轻易得使用其他第三方Python库。

## Setuptools + Pip

> The most crucial third-party Python software of all is Setuptools, which extends the packaging and installation facilities provided by the distutils in the standard library. Once you add Setuptools to your Python system you can download and install any compliant Python software product with a single command. It also enables you to add this network installation capability to your own Python software with very little work.

最重要的第三方Python软件就是Setuptools，它能够扩展由标准库中的distutils提供的包装和安装设施。一旦你添加`Setuptools`到你的Python系统中，仅需一条命令就可以下载和安装任何兼容的Python软件产品。它也让你可以通过很少的工作量就将这种网络安装能力添加到自己的Python软件中。

> To obtain the latest version of Setuptools for Windows, run the Python script available here: [ez_setup.py](https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py)

为了获得最新的Windows版`Setuptools`，可以运行Python脚本：[ez_setup.py](https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py)

> You’ll now have a new command available to you: `easy_install`. It is considered by many to be deprecated, so we will install its replacement: `pip`. Pip allows for uninstallation of packages, and is actively maintained, unlike `easy_install`.

你现在拥有一条可用的新命令：`easy_install`。但是它已经被很多人弃用了，所以我们将安装它的替代品：`pip`。`pip`比`easy_install`好在它可以卸载一个包，还被积极维护着。

> To install pip, run the Python script available here: [get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py)

为了安装`pip`，可以运行Python脚本：[get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py)

## Virtual Environments（虚拟环境）

> A Virtual Environment is a tool to keep the dependencies required by different projects in separate places, by creating virtual Python environments for them. It solves the “Project X depends on version 1.x but, Project Y needs 4.x” dilemma, and keeps your global site-packages directory clean and manageable.

Virtual Environment是一种隔离依赖的工具，通过创建虚拟Python环境来保持不同项目在单独的地方。它解决了“项目X依赖版本1.x但是项目Y需要4.x”这种困境，可以保证你的总包目录是干净的和可管理的。

> For example, you can work on a project which requires Django 1.3 while also maintaining a project which requires Django 1.0.

例如，你可以在一个依赖Django 1.3的项目上工具，也可以同时维护一个需要Django 1.0的项目。

> To start using and see more information: [Virtual Environments](http://github.com/kennethreitz/python-guide/blob/master/docs/dev/virtualenvs.rst) docs.

开始使用，查看更多信息：[Virtual Environments](http://github.com/kennethreitz/python-guide/blob/master/docs/dev/virtualenvs.rst)文档。
