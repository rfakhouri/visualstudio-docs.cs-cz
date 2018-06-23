---
title: Vytváření stránek aplikací pro službu SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, Web pages
- SharePoint development in Visual Studio, content pages
- SharePoint development in Visual Studio, application pages
- application pages [SharePoint development in Visual Studio], developing
- application pages [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7faa1e88a37416db85624863968e13b28de40bc6
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326124"
---
# <a name="create-application-pages-for-sharepoint"></a>Vytváření stránek aplikací pro službu SharePoint
  *Stránky aplikace* představuje stránku ASP.NET Web, který je určen k použití na webu služby SharePoint. Stránky aplikací se speciálním typem stránku ASP.NET. Hlavní rozdíl mezi stránky aplikace a standardní stránky ASP.NET je, že stránky aplikace obsahuje obsah, který je sloučen s hlavní stránku služby SharePoint. Na hlavní stránce umožňuje stránky aplikace sdílet stejný vzhled a chování jako ostatní stránky v lokalitě.  
  
 Visual Studio umožňuje návrh stránek aplikací pomocí návrháře. Návrhář zobrazí oblast obsahu pro každý zástupný symbol obsahu, který je definován na hlavní stránce. Stránka aplikace můžete navrhnout přetažením ovládacích prvků do těchto oblastí obsahu.  
  
## <a name="application-pages"></a>Stránky aplikací
 Stránky aplikací jsou sdíleny ve všech lokalitách na serveru, zatímco stránky webu je specifická pro jednu lokalitu. Další informace najdete [typy stránek SharePoint](http://go.microsoft.com/fwlink/?LinkID=211584).  
  
 Ve výchozím nastavení většina stránek, které se při vytváření webu služby SharePoint jsou stránky webu. Stránka serveru lze přidat do knihovny služby SharePoint stránky. Uživatele můžete přizpůsobit stránky webu pomocí nástrojů, jako je například návrháře služby SharePoint. Na stránce lokality můžou hostovat taky funkce, jako je dynamické webové části a zóny webových částí.  
  
 Stránky aplikací nemůžete provádět tyto akce. Ale stránky aplikace je nejlepší typ stránky vytvořit, pokud se má stránka obsahovat vlastní kód. I když můžete přidat vlastní kód na stránku lokality, kód zastaví spuštěn, když uživatel upravuje stránce pomocí nástrojů, jako je například návrháře služby SharePoint.  
  
> [!NOTE]  
>  Visual Studio neposkytuje šablony, které vám pomohou vytvářet weby pro web služby SharePoint. Další informace najdete v tématu [typy stránek SharePoint](http://go.microsoft.com/fwlink/?LinkID=211584).  
  
## <a name="create-an-application-page"></a>Vytvoření stránky aplikace
 Chcete-li vytvořit stránku aplikace, přidejte **stránky aplikace** položky projektu služby SharePoint. Při vytváření stránky aplikace Visual Studio přidá následující složky projektu:  
  
|Folder|Popis|  
|------------|-----------------|  
|Rozložení|Přiřadí se k virtuálnímu adresáři _layouts systému souborů služby SharePoint.|  
|Rozložení podsložky|Obsahuje soubory, které tvoří stránky aplikace. Ve výchozím nastavení tato složka obsahuje stejný název jako projektu. Kdykoli můžete přejmenovat této složky. Při spuštění projektu sady Visual Studio nasadí této složky na virtuální adresář _layouts systému souborů služby SharePoint.|  
  
 Visual Studio. přidá následující soubory do projektu:  
  
|Soubor|Popis|  
|----------|-----------------|  
|Soubor stránky ASP.NET (*.aspx*)|Obsahuje kód XML, který definuje stránky.|  
|Soubor kódu stránky aplikace|Obsahuje kódu stránky aplikace. Přidejte kód, který zpracovává události do tohoto souboru.|  
|Soubor návrháře kódu stránky aplikace|Obsahuje kód, který je generován návrháře. Neupravujte přímo tento soubor.|  
  
## <a name="design-and-debug-an-application-page"></a>Návrh a ladění stránky aplikace
 Návrh obsah stránky aplikace pomocí návrháře zobrazení v sadě Visual Studio. Tento návrhář se zobrazí, když otevřete stránku aplikace v projektu (poklepáním nebo otevřením jeho místní nabídky a pak vyberete **otevřete**) a potom zvolte **návrhu** tlačítko v dolní části editor.  
  
> [!NOTE]  
>  Stránky můžete navrhnout pouze v **zdroj** zobrazení návrháře. **Návrhu** zobrazení návrháře je zakázán pro stránky aplikací.  
  
 Stránky aplikace můžete ladit, stejně jako ostatní položky projektu služby SharePoint v sadě Visual Studio by ladění. Při spuštění ladicího programu sady Visual Studio, Visual Studio otevře web služby SharePoint.  
  
 Pokud chcete zobrazit stránku aplikace, je nutné ručně přejít do umístění souboru stránky aplikace (například: http://*název_serveru*adresáři /_layouts/*název_projektu*/ApplicationPage1.aspx).  
  
 Další informace o ladění projektů služby SharePoint, naleznete v části [řešení řešení služby SharePoint](../sharepoint/troubleshooting-sharepoint-solutions.md).  
  
## <a name="choose-a-master-page"></a>Vyberte stránku předlohy
 Ve výchozím nastavení **stránky aplikace** položku odkazuje na hlavní stránku webu, který používáte k ladění projektu. Že stránka s názvem v4.master a najdete ji v uvedených **Galerie stránky předlohy** webu služby SharePoint.  
  
 Můžete explicitně změnit, které stránky předlohy používá stránka aplikace nastavením `MasterPageFile` atribut aplikace `Page` elementu. (Příklad: `MasterPageFile="~/_layouts/applicationv4.master"`). Ve skutečnosti je nutné nastavit tento atribut, pokud na serveru SharePoint nejsou povoleny dynamické stránky předlohy. Další informace o hlavní stránky ve službě SharePoint, naleznete v části [stránky předlohy](http://go.microsoft.com/fwlink/?LinkID=169281).  
  
## <a name="see-also"></a>Viz také:
 [Vývoj pro SharePoint Foundation podrobněji](http://go.microsoft.com/fwlink/?LinkID=182103)   
 [Přehled technologie ASP.NET](/aspnet/overview)   
 [Webové stránky ASP.NET](/aspnet/web-pages/index)   
  
