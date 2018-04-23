---
title: Vytváření balíčků zaváděcího nástroje | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 794d569504e46627c9387046b381fdb843a7818e
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="creating-bootstrapper-packages"></a>Vytváření balíčků zaváděcího nástroje
Instalační program je obecný instalační program, který je možné nakonfigurovat na zjištění a instalace distribuovatelné součásti, jako jsou soubory Instalační služby systému Windows (.msi) a spustitelné programy. Instalační program je také označován jako zaváděcí nástroj. Je naprogramovaný tak, pomocí sady manifesty XML, které určují metadata pro správu instalace součásti.  
  
 Zavaděč nejprve zjišťuje, jestli všechny požadované součásti jsou již nainstalovány. Pokud požadavky nejsou nainstalovány, nejprve zavaděč zobrazí licenční smlouvy. Druhý po koncový uživatel přijme podmínky licenční smlouvy, začne instalace požadavky. Jinak hodnota pokud jsou všechny požadované součásti zjištěny, zaváděcí nástroj se spustí instalační program aplikace.  
  
## <a name="creating-custom-packages"></a>Vytváření vlastních balíčků  
 Manifesty můžete vygenerovat pomocí editoru XML v sadě Visual Studio. Další informace najdete v tématu [postupy: vytvoření balíčku Manifest](../deployment/how-to-create-a-package-manifest.md) a [postupy: vytvoření produktu Manifest](../deployment/how-to-create-a-product-manifest.md). Příklad vytvoření balíčku zaváděcího nástroje najdete v sekci [návod: vytvoření vlastní zavaděč zobrazit výzva ochranu osobních údajů](../deployment/walkthrough-creating-a-custom-bootstrapper-to-show-a-privacy-prompt.md).  
  
 Chcete-li vytvořit balíček zaváděcího nástroje, budete muset zadat redistribuovatelný balíček ve formě EXE nebo MSI do generátor manifestu zaváděcího nástroje. Generátor manifestu zaváděcího nástroje potom vytvoří následující soubory:  
  
-   Manifest produktu product.xml obsahující všechny jazykově neutrální metadat balíčku. Tato položka obsahuje metadata, které jsou společné pro všechny lokalizované verze distribuovatelné součásti.  
  
-   Manifest balíčku package.xml, který obsahuje metadata pro konkrétní jazyk; obvykle obsahuje lokalizované chybové zprávy. Součást musí mít alespoň jeden manifest balíčku pro každou lokalizované verzi této součásti.  
  
 Po vytvoření jsou tyto soubory, uložte do složky s názvem pro vlastního zaváděcího nástroje souboru manifestu produktu. Soubor manifestu balíčku přejde do složky s názvem pro národní prostředí. Například pokud je soubor manifestu balíčku pro anglickou distribuci, uložte soubor do složky s názvem en. Tento postup opakujte pro každý národním prostředí, jako je například Japonsko pro japonštinu a de pro němčinu. Posledním zákaznický balíček zaváděcího nástroje může mít následující strukturu složek.  
  
 `CustomBootstrapperPackage`  
  
 `product.xml`  
  
 `CustomBootstrapper.msi`  
  
 `de`  
  
 `eula.rtf`  
  
 `package.xml`  
  
 `en`  
  
 `eula.rtf`  
  
 `package.xml`  
  
 `ja`  
  
 `eula.rtf`  
  
 `package.xml`  
  
 Nakonec zkopírujte redistribuovatelné soubory do umístění složky zaváděcího nástroje. Další informace najdete v tématu [postupy: vytvoření balíčku zaváděcího nástroje lokalizované](../deployment/how-to-create-a-localized-bootstrapper-package.md).  
  
```  
\Program Files\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages  
```  
  
 or  
  
```  
\Program Files (x86)\Microsoft Visual Studio 14.0\SDK\Bootstrapper\Packages  
```  
  
 Můžete také určit umístění složky zaváděcího nástroje z **cesta** hodnotu v následujícím klíči registru:  
  
```  
HKLM\Software\Microsoft\GenericBootstrapper\11.0  
```  
  
 V 64bitových systémech použijte následující klíč registru:  
  
```  
HKLM\Software\Wow6432Node\Microsoft\GenericBootstrapper\11.0  
```  
  
 Každý distribuovatelná součást se zobrazí ve vlastní podsložce v adresáři balíčku. Produkt manifestu a redistribuovatelné soubory jsou umístěny do této podsložky. Lokalizované verze součásti a balíček manifesty jsou vloženy do podsložky pojmenované podle jazykové verze.  
  
 Po tyto soubory budou zkopírovány do složky, balíček zaváděcího nástroje se automaticky zobrazí v dialogovém okně požadavky sady Visual Studio. Pokud vaše zákaznický balíček zaváděcího nástroje nezobrazí, zavřete a znovu otevřete dialogové okno požadavky. Další informace najdete v tématu [dialogové okno požadavky](../ide/reference/prerequisites-dialog-box.md).  
  
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
  
 Seznamu redistributable je soubor XML, který by měl název v následujícím formátu: *název společnosti*. *Název komponenty*. RedistList.xml. Ano například pokud součást nazývá Datawidgets provedená: MSN, použijte Acme.DataWidgets.RedistList.xml. Příklad seznamu redistributable obsahu může vypadat přibližně takto:  
  
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