---
title: "Ukázka rozšíření aplikace Excel: Třída Technologymanager | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a7b760d-b5ac-4451-9593-6ac1a0b95cdb
caps.latest.revision: "9"
ms.author: douge
manager: douge
ms.openlocfilehash: 1932646809cba6c6211f87965ffee82e918c6882
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="sample-excel-extension-technologymanager-class"></a>Ukázka rozšíření aplikace Excel: třída TechnologyManager
Tato třída rozšiřuje <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager> třídy a poskytuje základní služby pro [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] rozšíření. Přestože základní třída má mnoho způsobů, jenom některé z nich se používá v této ukázce.  
  
 Některé metody právě vrátí hodnotu vlastnosti. Mnoho z metod jsou určeny k umožňuje vývojářům přepsat výchozí nastavení, které algoritmy sestavení do modulu programových testů uživatelského rozhraní. Tyto metody throw <xref:System.NotSupportedException> , nebo může vracet `null`, která sděluje rozhraní používat výchozí algoritmus.  
  
 V závislosti na složitosti základní technologii vývoj kód Správce technologie může trvat několik týdnů až o několik měsíců. Excel poskytuje možnost vytvořit technologie potenciálně velmi rozsáhlé správci. Tento příklad je záměrně omezen na listech aplikace Excel a buněk a používá omezené formátování.  
  
 Když je možné, používá kód Správce technologie .NET Remoting kanál otevřít `Communicator` třída extrahovat informace z doplněk spuštěných v procesu aplikace Excel.  
  
## <a name="com-visibility"></a>Přehled modelu COM  
 Všimněte si, že tato třída a každý z elementu třídy, rozšířit <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> třídy mají <xref:System.Runtime.InteropServices.ComVisibleAttribute> s hodnotou `true` třídy jsou viditelné modelu COM.  
  
## <a name="technologyname-property"></a>Vlastnost TechnologyName  
 Toto přepsání <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.TechnologyName%2A?displayProperty=fullName> vlastnost musíte zadat jedinečný a smysluplný název, který identifikuje základní technologii pro každou součást rozšíření. Pro tuto příponu hodnota je "Excel".  
  
## <a name="getcontrolsupportlevel-method"></a>GetControlSupportLevel – metoda  
 Toto přepsání <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetControlSupportLevel%2A?displayProperty=fullName> metoda vrátí číslo, které informuje o úrovni podpory, který správce technologie nabízejí pro ovládací prvek reprezentována Zadaný popisovač. Čím vrácené hodnoty, další technologie správce může podporovat ovládacího prvku. V takovém případě metoda zkontroluje okno, které obsahuje ovládací prvek a pokud je listu aplikace Excel, vrátí metoda nejvyšší hodnotou; Funkce nulové hodnoty, který označuje, že žádná podpora je k dispozici.  
  
## <a name="methods-to-get-an-element"></a>Metody k získání Element  
 Existuje několik důležitých metod, které se používají rozhraním framework programové testování uživatelského rozhraní pro získání element specifické pro technologie tím, že poskytuje popisovač, bod na obrazovce nebo element z jiné technologie. Kód pro tyto metody jsou není potřeba vysvětlovat. Základní metody jsou následující:  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetFocusedElement%2A?displayProperty=fullName>  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetElementFromPoint%2A?displayProperty=fullName>  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetElementFromWindowHandle%2A?displayProperty=fullName>  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.GetElementFromNativeElement%2A?displayProperty=fullName>  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.ConvertToThisTechnology%2A?displayProperty=fullName>  
  
## <a name="parsequeryid-method"></a>ParseQueryId – metoda  
 Když je vytvořen programového testu uživatelského rozhraní, uživatel může zadat hodnoty vlastností pro některé nebo všechny ovládací prvky v testu. Hodnoty těchto vlastností jsou používány rozhraní testování k vytvoření dvojice název hodnota volána vlastnosti vyhledávání, které se používají k vyhledání konkrétní ovládacích prvků uživatelského rozhraní během testu. Všechny vlastnosti vyhledávání společně představují hodnotu <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A?displayProperty=fullName> vlastnosti všech prvků technologii, která obsahuje každý ovládací prvek. Protože ovládacího prvku chtít najít několikrát během testu, tato metoda poskytuje správce technologie způsob, jak optimalizovat analýze vlastností vyhledávání pro daný ovládací prvek. Tato metoda také vrátí hodnotu souboru cookie, který můžete použít rozhraní pro následné vyhledávání pro ovládací prvek. Tato implementace metody používá <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.AndCondition.Match%2A?displayProperty=fullName> metoda analyzovat vlastností vyhledávání.  
  
## <a name="matchelement-method"></a>MatchElement – metoda  
 K provedení ovládacího prvku vyhledávání pomocí Správce technologie, můžete implementovat <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.Search%2A?displayProperty=fullName> metoda vrátí pole možné shody, nebo throw <xref:System.NotSupportedException>, která sděluje rozhraní používat vlastní vyhledávací algoritmus. V obou případech je nutné implementovat <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager.MatchElement%2A> metoda, kde se používá tato implementace znovu <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.AndCondition.Match%2A?displayProperty=fullName> metoda.  
  
## <a name="navigation-methods"></a>Navigační metody  
 Tyto metody získat nadřazené, děti nebo na stejné úrovni zadaného elementu ze hierarchie uživatelského rozhraní. Kód je jednoduchý a jasně komentáři.  
  
## <a name="getexcelelement-internal-method"></a>Interní metoda GetExcelElement  
 Tato interní metoda přebírá popisovač okna a informace o elementu aplikace Excel a vrátí požadovaný element aplikace Excel.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager>   
 <xref:System.NotSupportedException>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>   
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A>   
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
