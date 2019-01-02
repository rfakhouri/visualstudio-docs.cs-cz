---
title: Vytváření stránek pro službu SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, master pages
- SharePoint development in Visual Studio, page layouts
- SharePoint development in Visual Studio, content pages
- master pages[SharePoint development in Visual Studio], designing
- content pages[SharePoint development in Visual Studio], designing
- page layouts[SharePoint development in Visual Studio], designing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 71f0a75678c0123853f128f42bfdbf1c75ac0c74
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53859812"
---
# <a name="create-pages-for-sharepoint"></a>Vytváření stránek pro službu SharePoint
  Můžete vytvořit stránky aplikace, weby, stránky předlohy a rozložení stránek webu služby SharePoint.  
  
 Stránky aplikací můžete vytvořit pomocí šablony v sadě Visual Studio. Vytvoření stránky, stránky předlohy a rozložení stránek pomocí návrháře služby SharePoint. Pak můžete importovat tyto stránky do sady Visual Studio pro použití v projektu služby SharePoint.  
  
 Můžete také upravit vzhled a chování stránky s použitím šablony stylů CSS, ECMAScript a motivů.  
  
## <a name="types-of-sharepoint-pages"></a>Typy stránek služby SharePoint
 Následující tabulka popisuje čtyři hlavní typy stránek, které obsahuje web služby SharePoint.  
  
|Typ stránky|Popis|  
|---------------|-----------------|  
|Stránky aplikací|Vytvoření stránky aplikace, pokud chcete stránku tak, aby obsahovala vlastní kód nebo chcete stránku sdílet mezi více servery. Stránka webu v opačném případě může být nejlepší volbou.|  
|Stránky webu|Vytvoření stránky webu, pokud chcete provádět následující úkoly:<br /><br /> -Přidáte na stránku do knihovny služby SharePoint.<br />-Aktivovat stránku hostitele funkce jako dynamické webové části a zóny webové části.<br />-Umožňují uživatelům přizpůsobit stránky s použitím návrháře služby SharePoint.<br /><br /> Pokud chcete, aby stránka obsahuje vlastní kód není vytvoření stránky webu. I když přidáte vlastní kód na stránku webu, se zastaví kód spuštěn, když uživatel přizpůsobuje stránky s použitím návrháře služby SharePoint.|  
|Stránky předlohy|Vytvoření stránky předlohy, pokud chcete definovat společnou strukturu pro stránky a stránky aplikace.|  
|Rozložení stránek|Rozložení stránek, které jsou specifické pro [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] a umožňují definovat další běžné strukturu pro stránky a stránky aplikace.|  
  
 Přehled každý typ stránky, naleznete v tématu [stavebních bloků: Stránky a uživatelské rozhraní](http://go.microsoft.com/fwlink/?LinkID=182095), a [stránce rozložení a stránkami předloh](http://go.microsoft.com/fwlink/?LinkID=182096).  
  
## <a name="create-application-pages"></a>Vytvoření stránky aplikace
 Stránky aplikací v sadě Visual Studio můžete vytvořit přidáním **stránky aplikace** položky projektu služby SharePoint. Můžete přidat ovládací prvky na stránku a pak zpracovat události ovládacího prvku přidáním kódu.  
  
 Můžete nastavit zarážky v souboru kódu stránky, spusťte ladicí program a otestovat stránku na místním Sharepointovém webu bez provedení všech dalších kroků konfigurace. Další informace najdete v tématu [vytváření stránek aplikací pro SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md).  
  
## <a name="create-site-pages-master-pages-and-page-layouts"></a>Vytvoření stránky, stránky předlohy a rozložení stránek
 Můžete vytvořit stránky, stránky předlohy a rozložení stránek pomocí návrháře služby SharePoint. Pak můžete importovat tyto stránky do sady Visual Studio. Pokud chcete využít výhod nasazení nebo funkce správy zdrojového kódu, které jsou k dispozici v sadě Visual Studio umožňuje importujte vaše stránky. Další informace najdete v tématu [import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md).  
  
 Protože je obtížné upravit tyto stránky po importu, měli byste navrhnout tyto stránky před importem.  
  
## <a name="create-cascading-style-sheets-ecmascript-and-themes"></a>Vytvoření šablony stylů CSS, ECMAScript a motivů
 Visual Studio neposkytuje šablony pro vývoj stylů CSS (Cascading Style), ECMAScript (JavaScript nebo JScript) nebo soubory motivu pro weby služby SharePoint. Tyto soubory můžete vytvořit pomocí doprovodné materiály k dispozici v sadě SDK služby SharePoint nebo pomocí nástrojů, jako je SharePoint designeru.  
  
 Tyto soubory do svého řešení můžete přidat přímo nebo je importovat. V obou případech musíte vytvořit odpovídající mapované složky pro každou položku, která přidáte. Další informace o tom, jak vytvořit mapované složky, najdete v části [postupy: Přidání a odebrání mapovaných složek](../sharepoint/how-to-add-and-remove-mapped-folders.md).  
  
 Další informace o vytváření kaskádová šablona stylů, najdete v části [CSS stylu listů třídy využití ve službě SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkID=182098). Další informace o vytváření souborů JavaScript a JScript pro řešení služby SharePoint, naleznete v tématu [nastavení až základní stránku ASPX pro ECMAScript](http://go.microsoft.com/fwlink/?LinkID=182099). Další informace o motivech najdete v tématu [stavebních bloků: Stránky a uživatelské rozhraní](http://go.microsoft.com/fwlink/?LinkID=182095).  
  
## <a name="related-topics"></a>Související témata
  
|Název|Popis|  
|-----------|-----------------|  
|[Vytváření stránek aplikací pro SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)|Popisuje postup přidání stránky aplikace: *.aspx* obsah, který je sloučen s hlavní stránkou služby SharePoint.|  
|[Postupy: Vytvoření stránky aplikace](../sharepoint/how-to-create-an-application-page.md)|Ukazuje, jak vytvořit stránek ASP.NET, které běží na webu služby SharePoint.|  
|[Návod: Vytvoření stránky aplikace služby SharePoint](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)|Ukazuje, jak navrhovat a ladit webové stránky ASP.NET pro web služby SharePoint.|  
