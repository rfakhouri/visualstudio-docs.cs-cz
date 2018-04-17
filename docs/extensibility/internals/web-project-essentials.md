---
title: Webový projekt Essentials | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- web projects, essentials
ms.assetid: ca2f4e43-322c-4431-8680-52da846940bc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6918c539409a31dfe5249adb5858ca20c8c2337c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="web-project-essentials"></a>Webový projekt Essentials
Webové projekty vytvářet webové aplikace. Webového projektu slouží k vytvoření webové aplikace, které má inteligentní webové stránky. Inteligentní webová stránka obsahuje kódu na straně serveru, který vykreslí webovou stránku na vyžádání.  
  
 Pomocí tradičních programovacích jazyků, jako třeba [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] nebo [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], můžete vytvořit inteligentní webové stránky ke shromažďování a zpracování informací od uživatele, uchovávat v databázi a tak dále.  
  
-   Model kódu přidruží webové stránky, které mají soubor rozšíření .aspx nebo .asmx soubory závislé zdrojového kódu. Například možná hello.aspx hello.aspx.cs závislé zdrojovém kódu souboru.  
  
-   Na straně serveru kód spojený s inteligentní webové stránky zkompilován spustitelný soubor, který je umístěný ve složce/Bin webové stránky.  
  
-   Další zdrojové soubory kódu, například pomocných tříd, které nejsou přidružené konkrétní webovou stránku, jsou umístěny ve složce /App_Code webu.  
  
    -   Webový projekt (WSP) generuje jeden spustitelný soubor pro každou inteligentní webovou stránku. Další spustitelné soubory jsou generovány z jakékoli soubory zdrojového kódu ve složce /App_Code.  
  
    -   Projekt webové aplikace (WAP) vytvoří jeden spustitelný soubor, který kombinuje kód pro všechny inteligentní webové stránky, stejně jako všechny zdrojové soubory ve složce /App_Code.  
  
-   Soubor řešení pro webový projekt se nachází odděleně od přímo na webovém serveru. Ve výchozím nastavení, jsou umístěné v \Documents and Settings soubory řešení\\*YourAccount*dokumenty \My\\*\<Visual Studio ### >*\Projects\\ *YourWebSite*.  
  
    > [!NOTE]
    >  Pokud chcete zachovat soubor řešení s webovou stránku, data přesunout existuje a znovu jej otevřete.  
  
-   Pokud otevřete web, který nemá soubor řešení v sadě Visual Studio, je pro ni automaticky vygenerován nový soubor řešení.  
  
-   Webové projekty mít žádné soubory projektu. Informace o projektu je uložené v souboru řešení, v souboru web.config a jinde.  
  
-   Přidání vlastnosti globálních do webového projektu automaticky vytvoří soubor úložiště ve složce řešení webového projektu.  
  
-   Inteligentní webové stránky může být přidružen programovací jazyk na straně serveru pomocí Page – direktiva nebo \<skript runat = "server" > značky.  
  
-   Kromě toho webové stránky může mít libovolný počet klientské skriptování bloky napsané v jakékoli skriptovací jazyk.  
  
-   Systém lokality webového projektu se implementuje přidáním šablon projektů a položek a registraci [!INCLUDE[vwprvw](../../extensibility/internals/includes/vwprvw_md.md)] projektu.  
  
-   WAP systému je implementovaný jako projektu podtypem, označované taky jako příchuť projektu. [!INCLUDE[vwprvw](../../extensibility/internals/includes/vwprvw_md.md)] Projektu je specifického ve WAP dílčí vytvořit WAP systému. Další informace o projektu podtypů najdete v tématu [projektu podtypů](../../extensibility/internals/project-subtypes.md).  
  
-   Inteligentní webové stránky kombinuje HTML pomocí programovacího jazyka na straně serveru. Na straně serveru jazyk, se nazývá obsažené jazyk. Pro podporu obsažené jazyk, musí implementovat systém webového projektu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> rodiny rozhraní.  
  
    -   Pro podporu jazyka obsažené v editoru, musí služba jazyka HTML odložení zobrazení Kód obsažené jazyka službě obsažené jazyk.  
  
    -   Chyba značky (red squigglies) má být vytvořena vždy v editoru kódu primární vyrovnávací paměti.  
  
## <a name="see-also"></a>Viz také  
 [Webové projekty](../../extensibility/internals/web-projects.md)