---
title: 'Postupy: vytvoření manifestu produktu | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- product files [ClickOnce]
- product files [Windows Installer]
- prerequisites, custom bootstrapper package
- dependencies, custom bootstrapper package
ms.assetid: 2d316aaa-8bc0-4ce5-90ab-23b3eac0b5dd
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 116a54bae39738f95503ae9ca6e6cbac45c2db47
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-product-manifest"></a>Postupy: Vytvoření manifestu produktu
K nasazení požadovaných součástí pro aplikaci, můžete vytvořit balíček zaváděcího nástroje. Balíček zaváděcího nástroje obsahuje jeden produkt soubor manifestu ale manifest balíčku pro každé národní prostředí. Manifest balíčku obsahuje lokalizace specifické aspekty vašeho balíčku. To zahrnuje řetězce, licenční smlouvy s koncovým uživatelem a jazykové sady.  
  
 Další informace o manifestech produktu najdete v tématu [postupy: vytvoření balíčku Manifest](../deployment/how-to-create-a-package-manifest.md).  
  
## <a name="creating-the-product-manifest"></a>Vytvoření manifestu produktu  
  
#### <a name="to-create-the-product-manifest"></a>K vytvoření manifestu produktu  
  
1.  Vytvořte adresář pro balíček zaváděcího nástroje. Tento příklad používá C:\package.  
  
2.  V sadě Visual Studio vytvořte nový soubor XML s názvem `product.xml`a uložte ho do složky C:\package.  
  
3.  Přidejte následující kód XML pro popis oboru názvů a produktu kód XML pro balíček. Nahraďte kód produktu jedinečný identifikátor pro balíček.  
  
    ```  
    <Product  
    xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"   
    ProductCode="Custom.Bootstrapper.Package">  
    ```  
  
4.  Přidejte XML k určení, zda balíček obsahuje závislost. Tento příklad používá závislost na systému Windows verze 3.1.  
  
    ```  
    <RelatedProducts>  
        <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />  
      </RelatedProducts>  
    ```  
  
5.  Přidejte XML pro všechny soubory, které jsou v balíčku zaváděcího nástroje. Tento příklad používá název souboru balíčku CorePackage.msi.  
  
    ```  
    <PackageFiles>  
        <PackageFile Name="CorePackage.msi"/>  
    </PackageFiles>  
    ```  
  
6.  Zkopírovat nebo přesunout soubor CorePackage.msi do složky C:\package.  
  
7.  Přidejte XML tak, aby nainstalovat balíček pomocí příkazů zaváděcího nástroje. Zaváděcí nástroj automaticky přidá **/qn** příznak soubor .msi, který bude instalaci v bezobslužném režimu. Pokud je soubor .exe, zaváděcí nástroj spustí soubor .exe s použitím prostředí. Následující kód XML zobrazí CorePackage.msi žádné argumenty, ale argument příkazového řádku můžete vložit do atributu.  
  
    ```  
    <Commands>  
        <Command PackageFile="CorePackage.msi" Arguments="">  
    ```  
  
8.  Přidejte následující kód XML pro zkontrolujte, zda je nainstalován tento balíček zaváděcího nástroje. Nahraďte kód produktu identifikátor GUID pro komponentu redistributable.  
  
    ```  
    <InstallChecks>  
        <MsiProductCheck   
            Property="IsMsiInstalled"   
            Product="{XXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>  
    </InstallChecks>  
    ```  
  
9. Přidejte XML můžete změnit chování zaváděcího nástroje podle toho, pokud je již nainstalována součást zaváděcího nástroje. Pokud je nainstalována, balíček zaváděcího nástroje se nespustí. Následující kód XML kontroluje, zda je aktuální uživatel správcem, protože tato součást vyžaduje oprávnění správce.  
  
    ```  
    <InstallConditions>  
        <BypassIf   
           Property="IsMsiInstalled"   
           Compare="ValueGreaterThan" Value="0"/>  
        <FailIf Property="AdminUser"   
            Compare="ValueNotEqualTo" Value="True"  
            String="NotAnAdmin"/>  
    </InstallConditions>  
    ```  
  
10. Přidejte XML nastavit ukončovací kód, pokud je k úspěšnému dokončení instalace, a pokud je nutné restartovat počítač. Následující kód XML ukazuje, že Fail a FailReboot ukončovací kódy, které označují, že zavaděč nebude pokračovat v instalaci balíčků.  
  
    ```  
    <ExitCodes>  
        <ExitCode Value="0" Result="Success"/>  
        <ExitCode Value="1641" Result="SuccessReboot"/>  
        <ExitCode Value="3010" Result="SuccessReboot"/>  
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>  
    </ExitCodes>  
    ```  
  
11. Přidejte následující kód XML pro ukončení oddílu pro příkazy zaváděcího nástroje.  
  
    ```  
        </Command>  
    </Commands>  
    ```  
  
12. Přesuňte složku C:\package do adresáře zaváděcího nástroje Visual Studio. Pro Visual Studio 2010 je to adresář SDKs\Windows\v7.0A\Bootstrapper\Packages \Program Files\Microsoft.  
  
## <a name="example"></a>Příklad  
 Manifest produktu obsahuje pokyny k instalaci pro vlastní požadavky.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<Product  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  ProductCode="Custom.Bootstrapper.Package">  
  
  <RelatedProducts>  
    <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />  
  </RelatedProducts>  
  
  <PackageFiles>  
    <PackageFile Name="CorePackage.msi"/>  
  </PackageFiles>  
  
  <InstallChecks>  
    <MsiProductCheck Product="IsMsiInstalled"   
      Property="{XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>  
  </InstallChecks>  
  
  <Commands>  
    <Command PackageFile="CorePackage.msi" Arguments="">  
  
      <InstallConditions>  
        <BypassIf Property="IsMsiInstalled"  
          Compare="ValueGreaterThan" Value="0"/>  
        <FailIf Property="AdminUser"   
          Compare="ValueNotEqualTo" Value="True"  
         String="NotAnAdmin"/>  
      </InstallConditions>  
  
      <ExitCodes>  
        <ExitCode Value="0" Result="Success"/>  
        <ExitCode Value="1641" Result="SuccessReboot"/>  
        <ExitCode Value="3010" Result="SuccessReboot"/>  
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>  
      </ExitCodes>  
    </Command>  
  </Commands>  
</Product>  
```  
  
## <a name="see-also"></a>Viz také  
 [Referenční schéma balíčku a produktu](../deployment/product-and-package-schema-reference.md)