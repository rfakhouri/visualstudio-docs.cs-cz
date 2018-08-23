---
title: Použití modelu automatizace | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio SDK], automation model
ms.assetid: 0c7f7889-fbfb-4b19-804f-b742138baecd
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: da79ac654f37b8f9fd9ceaa1eac3df09204f7196
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676082"
---
# <a name="using-the-automation-model"></a>Použití modelu automatizace
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [pomocí modelu automatizace](https://docs.microsoft.com/visualstudio/extensibility/internals/using-the-automation-model).  
  
Po připojení vaší VSPackage automatizace, lze získat vlastnosti a metody voláním <xref:EnvDTE.DTEClass.GetObject%2A> metodu <xref:EnvDTE._DTE> objekt předáním řetězce představující objekt, který chcete načíst.  
  
## <a name="obtaining-project-objects"></a>Získávání objektů projektu  
 Následují dva příklady kódu, které ukazují, jak spotřebitel automatizace získá projektu objekty automatizace. Informace o tom, jak získat objekt DTE najdete v tématu [postupy: získání odkazy objekty DTE a DTE2](http://msdn.microsoft.com/library/c92e3c8e-82e6-4a67-85da-e43c50ffd8e4).  
  
```vb  
Sub DoAutomation()  
    Dim MyProjects As Projects  
    MyProjects = DTE.GetObject("AcmeProject")  
End Sub  
```  
  
```cpp#  
void DoAutomation(void)  
{  
  CComQIPtr<Projects> pMyPkg; // Use an IDispatch-derived object type.  
    pMyPkg = pDTE->GetObject("AcmeProjects");   
  
   // The '=' performs a Query Interface.  
   // Assumes pDTE is already available as a global.  
   // Use pMyPkg to access your projects object's properties and methods.  
}  
  
```  
  
 V tomto okamžiku můžete použít standardní projekt objekty, které jsou součástí konkrétního balíčku VSPackage přesunout dolů hierarchickému modelu.  
  
 Následující příklad kódu ukazuje, jak získat vlastní objekt, který je součástí do vlastního typu projektu.:  
  
```vb  
Dim MyPrj As Project  
Dim MyPrjItem As ProjectItem  
Dim objMyObject as MyExtendedObject  
  
MyPrj = MyProjects.Item(1) 'use the Projects collection to get a project  
objMyObject = MyPrj.Object 'You call .Object to get to special Project  
                           'implementation  
objMyObject.MySpecialMethodOrProperty  
```  
  
 Následující kód obsahuje seznam všech vlastností v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] prostředí **Obecné** možnost **nástroje** nabídky:  
  
```vb  
dim objDTE  
dim objEnv  
set objDTE = CreateObject("VisualStudio.DTE")  
set objEnv = objDTE.Properties("Environment", "General")  
for each obj in ObjEnv  
MsgBox obj.Name  
Next  
  
```  
  
## <a name="see-also"></a>Viz také  
 <xref:EnvDTE.DTEClass.GetObject%2A>

