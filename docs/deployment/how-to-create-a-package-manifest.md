---
title: "Postupy: vytvoření manifestu balíčku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- package files [Windows Installer]
- package files [ClickOnce]
- prerequisites, custom bootstrapper package
- dependencies, custom bootstrapper packages
ms.assetid: 5aecc507-2764-42f2-ae6f-c227971cf0af
caps.latest.revision: "12"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 463286eb8360b728b3b7e3ce9396c9f4b7e11305
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-package-manifest"></a>Postupy: Vytvoření manifestu balíčku
K nasazení požadovaných součástí pro aplikaci, můžete použít balíček zaváděcího nástroje. Balíček zaváděcího nástroje obsahuje jeden produkt soubor manifestu ale manifest balíčku pro každé národní prostředí. Sdílené funkce přes různé lokalizované verze by měli přejít do manifestu produktu.  
  
 Další informace o balíčku manifesty najdete v tématu [postupy: vytvoření produktu Manifest](../deployment/how-to-create-a-product-manifest.md).  
  
## <a name="creating-the-package-manifest"></a>Vytvoření manifestu balíčku  
  
#### <a name="to-create-the-package-manifest"></a>Chcete-li vytvořit manifest balíčku  
  
1.  Vytvořte adresář pro balíček zaváděcího nástroje. Tento příklad používá C:\package.  
  
2.  Vytvořte podadresáři s názvem národní prostředí, jako je například en pro angličtinu.  
  
3.  V sadě Visual Studio, vytvořte soubor XML, který je pojmenován `package.xml`a uložte ho do složky C:\package\en.  
  
4.  Přidejte XML pro název balíčku zaváděcího nástroje, jazykovou verzi pro tohoto lokalizovaného manifestu balíčku a volitelné licenční smlouvy. Následující kód XML používá proměnné `DisplayName` a `Culture`, které jsou definovány v předchozím prvku.  
  
    ```  
    <Package  
        xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
        Name="DisplayName"  
        Culture="Culture"  
        LicenseAgreement="eula.txt">  
    ```  
  
5.  Přidejte XML pro všechny soubory, které jsou v adresáři specifická pro národní prostředí. Následující kód XML používá soubor s názvem eula.txt, které platí pro **en** národního prostředí.  
  
    ```  
    <PackageFiles>  
      <PackageFile Name="eula.txt"/>  
    </PackageFiles>  
    ```  
  
6.  Přidejte XML tak, aby definovat lokalizovatelný řetězce pro balíček zaváděcího nástroje. Následující kód XML přidá chyby řetězce pro národní prostředí cs.  
  
    ```  
      <Strings>  
        <String Name="DisplayName">Custom Bootstrapper Package</String>  
        <String Name="CultureName">en</String>  
        <String Name="NotAnAdmin">You must be an administrator to install   
    this package.</String>  
        <String Name="GeneralFailure">A general error has occurred while   
    installing this package.</String>  
    </Strings>  
    ```  
  
7.  Zkopírujte složku C:\package do adresáře zaváděcího nástroje Visual Studio. Pro Visual Studio 2010 je to adresář SDKs\Windows\v7.0A\Bootstrapper\Packages \Program Files\Microsoft.  
  
## <a name="example"></a>Příklad  
 Manifest balíčku obsahuje informace specifické pro národní prostředí, například chybové zprávy, licenční podmínky pro software a jazykových sad.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<Package  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  Name="DisplayName"  
  Culture="Culture"  
  LicenseAgreement="eula.txt">  
  
  <PackageFiles>  
    <PackageFile Name="eula.txt"/>  
  </PackageFiles>  
  
  <Strings>  
    <String Name="DisplayName">Custom Bootstrapper Package</String>  
    <String Name="Culture">en</String>  
    <String Name="NotAnAdmin">You must be an administrator to install this package.</String>  
    <String Name="GeneralFailure">A general error has occurred while   
installing this package.</String>  
  </Strings>  
</Package>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční schéma balíčku a produktu](../deployment/product-and-package-schema-reference.md)