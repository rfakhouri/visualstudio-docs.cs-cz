---
title: Registrace jeden soubor generátory | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, custom tools
- custom tools, defining registry settings
ms.assetid: db7592c0-1273-4843-9617-6e2ddabb6ca8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b9b7d16a9e473028d85540f4447d9981382be0fd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="registering-single-file-generators"></a>Registrace generátory jeden soubor
Chcete-li k dispozici v vlastní nástroj [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], je nutné zaregistrovat tak [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] můžete vytvořit instanci a přidruží ji s typem konkrétní projekt.  
  
### <a name="to-register-a-custom-tool"></a>Chcete-li zaregistrovat vlastní nástroj  
  
1.  Zaregistrovat nástroj vlastní knihovny DLL buď v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] místním registru nebo v registru systému, v části HKEY_CLASSES_ROOT.  
  
     Například je zde informace o registraci pro spravované MSDataSetGenerator vlastní nástroj, který se dodává s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]:  
  
    ```  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\CLSID\{E76D53CC-3D4F-40A2-BD4D-4F3419755476}]  
    @="COM+ class: Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"  
    "InprocServer32"="C:\\WINDOWS\\system32\\mscoree.dll"  
    "ThreadingModel"="Both"  
    "Class"="Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"  
    "Assembly"="Microsoft.VSDesigner, Version=14.0.0.0, Culture=Neutral, PublicKeyToken=b03f5f7f11d50a3a"  
    ```  
  
2.  Vytvořte klíč registru v požadované [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hive v části generátory\\*GUID* kde *GUID* identifikátor GUID nebo není definována konkrétní jazyk systému projektu služby. Název klíče bude programový název svůj vlastní nástroj. Vlastní nástroj klíč má následující hodnoty:  
  
    -   (Výchozí)  
  
         Volitelné. Obsahuje uživatelsky přívětivý popis vlastního nástroje. Tento parametr je volitelný, ale doporučujeme.  
  
    -   CLSID  
  
         Požadováno. Určuje identifikátor knihovny tříd komponenty modelu COM, který implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>.  
  
    -   GeneratesDesignTimeSource  
  
         Požadováno. Určuje, zda pro vizuální nástroje jsou k dispozici typy ze souborů vyprodukované tento vlastní nástroj. Hodnota tohoto parametru musí být 0 (nula) není k dispozici vizuální nástroje typy nebo 1 (jeden) pro typy, které jsou k dispozici pro vizuální nástroje.  
  
    > [!NOTE]
    >  Je nutné zaregistrovat vlastní nástroj zvlášť pro každý jazyk, pro které má být k dispozici vlastní nástroj.  
  
     Například MSDataSetGenerator registruje jednou pro každý jazyk:  
  
    ```  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{164b10b9-b200-11d0-8c61-00a0c91e29d5}\MSDataSetGenerator]  
    @="Microsoft VB Code Generator for XSD"  
    "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"  
    "GeneratesDesignTimeSource"=dword:00000001  
  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{fae04ec1-301f-11d3-bf4b-00c04f79efbc}\MSDataSetGenerator]  
    @="Microsoft C# Code Generator for XSD"  
    "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"  
    "GeneratesDesignTimeSource"=dword:00000001  
    ```  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>   
 [Implementace generátory jedním souborem](../../extensibility/internals/implementing-single-file-generators.md)   
 [Vystavení typy vizuální nástroje](../../extensibility/internals/exposing-types-to-visual-designers.md)   
 [Úvod k objektu Správce BuildManager](http://msdn.microsoft.com/en-us/50080ec2-c1c9-412c-98ef-18d7f895e7fa)