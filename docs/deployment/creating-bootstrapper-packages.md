---
title: Vytváření balíčků zaváděcího nástroje
ms.custom: ''
ms.date: 05/02/2018
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications [Visual Studio], prerequisites
- deploying applications [Visual Studio], custom prerequisites
- prerequisites, custom
- RedistList file
- custom prerequisites
- redistributables list
ms.assetid: ba1a785b-693d-446b-bcae-b88cadee73d1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 234f89f2d0a28c0836ee06df4c49c3ab60f102ce
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="create-bootstrapper-packages"></a>Vytváření balíčků zaváděcího nástroje
Instalační program je obecný instalační program, který je možné nakonfigurovat na zjištění a instalace distribuovatelné součásti, jako jsou soubory Instalační služby systému Windows (.msi) a spustitelné programy. Instalační program je také označován jako zaváděcí nástroj. Je naprogramovaný tak, pomocí sady manifesty XML, které určují metadata pro správu instalace součásti.  Každý distribuovatelné součásti, nebo požadovaných součástí, které se zobrazí v **požadavky** dialogové okno pro ClickOnce je balíček zaváděcího nástroje. Balíček zaváděcího nástroje je skupina adresářů a souborů, které obsahují manifestu soubory, které popisují, jak by měly být nainstalovány požadované součásti. 
  
Zavaděč nejprve zjišťuje, jestli všechny požadované součásti jsou již nainstalovány. Pokud požadavky nejsou nainstalovány, nejprve zavaděč zobrazí licenční smlouvy. Druhý po koncový uživatel přijme podmínky licenční smlouvy, začne instalace požadavky. Jinak hodnota pokud jsou všechny požadované součásti zjištěny, zaváděcí nástroj se spustí instalační program aplikace.  
  
## <a name="create-custom-bootstrapper-packages"></a>Vytvořit vlastní balíčky zaváděcího nástroje  
Manifesty zaváděcího nástroje můžete vygenerovat pomocí editoru XML v sadě Visual Studio. Příklad vytvoření balíčku zaváděcího nástroje najdete v sekci [návod: vytvoření vlastního zaváděcího nástroje s výzvou o ochraně osobních údajů](../deployment/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt.md).  
  
Chcete-li vytvořit balíček zaváděcího nástroje, máte k vytvoření manifestu produktu a, pro jednotlivé lokalizované verze komponenty, také manifestu balíčku.
  
* Manifest produktu *product.xml*, obsahuje veškerá metadata jazykově neutrální pro balíček. Tato položka obsahuje metadata, které jsou společné pro všechny lokalizované verze distribuovatelné součásti.  K vytvoření tohoto souboru, najdete v části [postupy: vytvoření produktu Manifest](../deployment/how-to-create-a-product-manifest.md).
  
* Manifest balíčku *package.xml*, obsahuje metadata pro konkrétní jazyk; obvykle obsahuje lokalizované chybové zprávy. Součást musí mít alespoň jeden manifest balíčku pro každou lokalizované verzi této součásti. K vytvoření tohoto souboru, najdete v části [postupy: vytvoření balíčku Manifest](../deployment/how-to-create-a-package-manifest.md).
  
Po vytvoření jsou tyto soubory, uložte do složky s názvem pro vlastního zaváděcího nástroje souboru manifestu produktu. Soubor manifestu balíčku přejde do složky s názvem pro národní prostředí. Například pokud je soubor manifestu balíčku pro anglickou distribuci, uložte soubor do složky s názvem en. Tento postup opakujte pro každý národním prostředí, jako je například Japonsko pro japonštinu a de pro němčinu. Posledním zákaznický balíček zaváděcího nástroje může mít následující strukturu složek.  

    ```
    CustomBootstrapperPackage
      product.xml
      CustomBootstrapper.msi
      de
        eula.rtf
        package.xml
      en
        eula.rtf
        package.xml
      ja
        eula.rtf
        package.xml
    ```
  
Zkopírujte redistribuovatelné soubory do umístění složky zaváděcího nástroje. Další informace najdete v tématu [postupy: vytvoření balíčku zaváděcího nástroje lokalizované](../deployment/how-to-create-a-localized-bootstrapper-package.md).
 
    *\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
    
or  
    
    *\Program Files (x86)\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages*
  
Můžete také určit umístění složky zaváděcího nástroje z **cesta** hodnotu v následujícím klíči registru:  
  
    *HKLM\Software\Microsoft\GenericBootstrapper\11.0*
  
Na 64bitových systémech použijte následující klíč registru:  
  
    *HKLM\Software\Wow6432Node\Microsoft\GenericBootstrapper\11.0*
  
Každý distribuovatelná součást se zobrazí ve vlastní podsložce v adresáři balíčku. Produkt manifestu a redistribuovatelné soubory musí být vloženy do této podsložky. Lokalizované verze součásti a balíček manifesty musíte umístit do podsložky pojmenované podle název jazykové verze.  
  
Po tyto soubory budou zkopírovány do složky, balíček zaváděcího nástroje v sadě Visual Studio automaticky zobrazí **požadavky** dialogové okno. Pokud vaše zákaznický balíček zaváděcího nástroje nezobrazí, zavřete a znovu otevřete **požadavky** dialogové okno. Další informace najdete v tématu [dialogové okno požadavky](../ide/reference/prerequisites-dialog-box.md).  
  
V následující tabulce jsou uvedeny vlastnosti, které se vyplní automaticky podle zaváděcí nástroj.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|ApplicationName|Název aplikace.|  
|ProcessorArchitecture|Procesor a bits slova platformy cílem spustitelný soubor. Následující hodnoty:<br /><br /> -Intel<br />-IA64<br />-AMD64|  
|[Version9x](https://msdn.microsoft.com/en-us/library/aa372490\(v=vs.140\).aspx)|Číslo verze pro operační systémy Microsoft Windows 95, Windows 98 nebo Windows mi. Syntaxe verze je Major.Minor.ServicePack.|  
|[VersionNT](https://msdn.microsoft.com/en-us/library/aa372495\(v=vs.140\).xaspx)|Číslo verze pro operační systémy Windows NT, Windows 2000, Windows XP, Windows Vista, Windows Server 2008 nebo Windows 7. Syntaxe verze je Major.Minor.ServicePack.|  
|[VersionMSI](https://msdn.microsoft.com/en-us/library/aa372493\(v=vs.140\).aspx)|Verze sestavení Instalační služby systému Windows (msi.dll) spustit během instalace.|  
|[AdminUser](https://msdn.microsoft.com/en-us/library/aa367545\(v=vs.140\).aspx)|Tato vlastnost nastavena, pokud má uživatel oprávnění správce. Hodnoty jsou true nebo false.|  
|InstallMode|Režim instalace označuje, kde je potřeba nainstalovat ze součásti. Následující hodnoty:<br /><br /> -HomeSite - požadované součásti jsou nainstalované z webu dodavatele.<br />-SpecificSite - požadované součásti jsou nainstalované z umístění, které vyberete.<br />-SameSite - požadované součásti jsou nainstalovány ze stejného umístění jako aplikace.|  
  
## <a name="separating-redistributables-from-application-installations"></a>Oddělení Redistributables z instalace aplikace  
Redistribuovatelné soubory můžete zabránit v projektech nastavení nasazovaný. K tomuto účelu vytvořte seznam redistributable ve složce RedistList ve vašem adresáři rozhraní .NET Framework:  
  
`%ProgramFiles%\Microsoft.NET\RedistList`  
  
Seznamu redistributable je soubor XML, který by měl název v následujícím formátu: *název společnosti*. *Název komponenty*. RedistList.xml. Ano, například pokud součást nazývá Datawidgets provedená: MSN, použít *Acme.DataWidgets.RedistList.xml*. Příklad seznamu redistributable obsahu může vypadat přibližně takto:  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<FileList Redist="Acme.DataWidgets" >  
<File AssemblyName="Acme.DataGrid" Version="1.0.0.0" PublicKeyToken="b03f5f7f11d50a3a" Culture="neutral" ProcessorArchitecture="MSIL" InGAC="true" />  
</FileList>  
```  
  
## <a name="see-also"></a>Viz také  
 [Postupy: instalace předpokladů s aplikací ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Dialogové okno požadavky](../ide/reference/prerequisites-dialog-box.md)   
 [Referenční schéma balíčku a produktu](../deployment/product-and-package-schema-reference.md)   
 [Použít Visual Studio 2005 zavaděč k nastartujte instalace](http://go.microsoft.com/fwlink/?LinkId=107537)