![](https://img.shields.io/badge/swift-5.0-green.svg)
![](https://img.shields.io/badge/VIPER-generamba-orange.svg)

Generamba Template with Dependency inversion ([EasyDi](https://github.com/AndreyZarembo/EasyDi) or [Swinject](https://github.com/Swinject/Swinject)), Storyboards ([Reusable](https://github.com/AliSoftware/Reusable)), Routing ([LightRoute](https://github.com/SpectralDragon/LightRoute)) and Tests ([Quick](https://github.com/Quick/Quick) + [Nible](https://github.com/Quick/Nimble))

# HOWTO:

1) [Install Generamba](https://github.com/AYastrebov/Generamba)

2) [Initialize Generamba](https://github.com/rambler-digital-solutions/Generamba/wiki/Available-Commands#basic-generamba-configuration) in your project's folder and install templates from this repo

3) open terminal and execute this in the same project's folder: 

To use with Swinject

```bash
$ generamba gen Module swift_viper_swinject
```

To use with EasyDi

```bash
$ generamba gen Module swift_viper_easydi
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
  └── Assembly
       ├── ModuleAssembly.swift 
       └── ModuleInitializer.swift (EasyDi only)
```
<!-- AUTO-GENERATED-CONTENT:END -->

If you use Swinject, add ```ApplicationAssembly``` file:

```swift
import Swinject
import SwinjectStoryboard

final class ApplicationAssembly {
    
    //Use default dependency
    class var assembler: Assembler {
        return Assembler([ApplicationModuleAssembly()])
    }
    
    var assembler: Assembler
    
    //If you want use custom Assembler
    init(with assemblies: [Assembly]) {
        assembler = Assembler(assemblies)
    }
}

//Inject dependency in Main Storyboard
extension SwinjectStoryboard {
    
    @objc class func setup() {
        defaultContainer = ApplicationAssembly.assembler.resolver as! Container
    }
}
```

Russian Federation, Saint-Petersburg, 2019
Yastrebov A.A.