---
title: Vytváření opakovaně použitelných ovládacích prvků webové části nebo stránky aplikací | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- user controls [SharePoint development in Visual Studio], creating
- SharePoint development in Visual Studio, user controls
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 71e67ab41fd39563520370eb079fca1b7c82015e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62952786"
---
# <a name="create-reusable-controls-for-web-parts-or-application-pages"></a>Vytvoření opakovaně použitelné ovládací prvky webové části nebo stránky aplikace
  V sadě Visual Studio můžete vytvořit vlastní, opakovaně použitelné ovládací prvky, které mohou být spotřebovány stránkami aplikace a webové části, která spustí v Sharepointu. Tyto ovládací prvky, se nazývají uživatelské ovládací prvky. Uživatelský ovládací prvek je druh složeného ovládacího prvku, který funguje podobně jako webová stránka ASP.NET – můžete přidat existující ovládací prvky webového serveru a značky uživatelského ovládacího prvku a definovat vlastnosti a metody ovládacího prvku. Potom je můžete vložit v ASP.NET Web pages, kde působí jako celek.

## <a name="create-a-user-control"></a>Vytvoření uživatelského ovládacího prvku
 Chcete-li vytvořit uživatelský ovládací prvek, přidejte **uživatelský ovládací prvek** do **prázdný projekt SharePoint**. Další informace najdete v tématu [jak: Vytvoření uživatelského ovládacího prvku pro části stránky nebo webové aplikace SharePoint](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md).

 Když přidáte **uživatelský ovládací prvek** položky, sady Visual Studio vytvoří složku ve vašem projektu a přidá několik souborů do složky. Následující tabulka popisuje každý soubor.

|Soubor|Popis|
|----------|-----------------|
|Soubor uživatelského ovládacího prvku|Definuje uživatelského ovládacího prvku. Návrh uživatelského ovládacího prvku tak, že přidáte ovládací prvky a značky k tomuto souboru.|
|Soubor kódu|Obsahuje kódu uživatelského ovládacího prvku. Přidejte kód pro zpracování událostí do tohoto souboru.|
|Soubor kódu návrháře|Obsahuje kód generovaný návrhářem a neměl by být upravován přímo.|

## <a name="design-the-user-control"></a>Návrh uživatelského ovládacího prvku
 Návrh uživatelského ovládacího prvku pomocí návrháře Visual Web Developer v sadě Visual Studio. Tento návrhář se zobrazí při otevření souboru uživatelského ovládacího prvku v projektu a zvolte **návrhu** kartu.

## <a name="consume-the-user-control"></a>Spotřebovat uživatelský ovládací prvek
 Uživatelské ovládací prvky v Sharepointu nezobrazí, dokud je vložíte do stránky aplikace nebo webové části.

 Zahrnout uživatelský ovládací prvek na stránce aplikace, otevřete webovou stránku, do které chcete přidat uživatelský ovládací prvek ASP.NET. Přepnout do zobrazení návrhu, pak vyberte soubor vlastního uživatelského ovládacího prvku v Průzkumníku řešení a přetáhněte ji na stránce. Uživatelský ovládací prvek ASP.NET je přidán na stránku a Návrhář vytvoří direktivy, které je potřeba pro stránky a rozpoznat uživatelského ovládacího prvku. Teď můžete pracovat s veřejné vlastnosti a metody ovládacího prvku.

 Chcete-li zahrnout uživatelský ovládací prvek webové části, přidat uživatelský ovládací prvek webové části <xref:System.Web.UI.WebControls.WebParts.Part.Controls%2A> kolekci do souboru kódu webové části. Následující příklad přidá uživatelský ovládací prvek <xref:System.Web.UI.WebControls.WebParts.Part.Controls%2A> kolekce webové části.

 [!code-vb[SP_VisualWebPart#5](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1.vb#5)]
 [!code-csharp[SP_VisualWebPart#5](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1.cs#5)]

## <a name="debug-a-user-control"></a>Ladění uživatelského ovládacího prvku
 Chcete-li ladit uživatelský ovládací prvek, ujistěte se, že uživatelský ovládací prvek součástí stránce aplikace nebo webové části v projektu služby SharePoint. Potom můžete ladit kód do uživatelského ovládacího prvku stejně, jako by ladění kódu v každém projektu Visual Studio.

 Při spuštění ladicího programu sady Visual Studio, Visual Studio otevře web služby SharePoint.

 V Sharepointu otevřete stránku aplikace, který obsahuje uživatelský ovládací prvek. Pokud uživatelský ovládací prvek je součástí webové části, přidáte webovou část na stránku webové části služby SharePoint.

 Další informace o ladění projektů SharePoint naleznete v tématu [řešení potíží s SharePoint](../sharepoint/troubleshooting-sharepoint-solutions.md).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Postupy: Vytvoření uživatelského ovládacího prvku pro části stránky nebo webové aplikace služby SharePoint](../sharepoint/how-to-create-a-user-control-for-a-sharepoint-application-page-or-web-part.md)|Ukazuje, jak vytvořit vlastní, opakovaně použitelné ovládací prvky, které mohou být spotřebovány stránkami aplikace a webové části, která spustí v Sharepointu.|
