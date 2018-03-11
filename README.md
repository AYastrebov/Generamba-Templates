![](https://img.shields.io/badge/swift-4.0-green.svg)
![](https://img.shields.io/badge/VIPER-generamba-orange.svg)


# HOWTO:


1) [Install Generamba](https://github.com/rambler-digital-solutions/Generamba)

2) [Initialize Generamba](https://github.com/rambler-digital-solutions/Generamba/wiki/Available-Commands#basic-generamba-configuration) in your project's folder and install templates from this repo

3) open terminal and execute this in the same project's folder: 
```bash
$ generamba gen Module swifty_viper
```

The new VIPER Module/Submodule(whatever) will be generated in your project's folder with structure:

<!-- AUTO-GENERATED-CONTENT:START (DIRTREE:dir=./) -->
```
Module
  ├── View
  │    ├── ModuleViewInput.swift
  │    ├── ModuleViewOutput.swift
  │    └── ModuleViewController.swift
  ├── Storyboard
  │    └── ModuleModuleStoryboard.storyboard
  ├── Presenter
  │    ├── ModuleModuleInput.swift
  │    └── ModulePresenter.swift
  ├── Interactor
  │    ├── ModuleInteractorInput.swift
  │    ├── ModuleInteractorOutput.swift
  │    └── ModuleInteractor.swift
  ├── Router
  │    ├── ModuleRouterInput.swift
  │    └── ModuleRouter.swift
  ├── Assembly
  │    ├── ModuleAssembly.swift 
  │    └── ModuleInitializer.swift
  └── Protocols
       └── ModuleProtocols.swift
```
<!-- AUTO-GENERATED-CONTENT:END -->

Russian Federation, Saint-Petersburg, 2018
Yastrebov A.A.