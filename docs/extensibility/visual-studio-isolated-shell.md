---
redirect_url: shell/visual-studio-isolated-shell
title: "Izolované prostředí sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shell [Visual Studio], shell-based applications, isolated mode
- Visual Studio shell, isolated mode
- isolated shell-based applications [Visual Studio]
- Visual Studio shell, shell-based applications, isolated mode
- Shell [Visual Studio], isolated mode
ms.assetid: d2620e71-be9e-44c9-b5b7-03a4c8d9cf0b
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dc6254be575593056c386360aa0d7c0a83833d75
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-isolated-shell"></a>Izolované prostředí sady Visual Studio
Prostředí sady Visual Studio izolované vám umožní vytvořit samostatné aplikace, které můžou běžet souběžně sdílená s jinými verzemi sady Visual Studio. Je použité především k hostování specializované nástroje, které můžete používat služby Visual Studio, ale také mít přizpůsobený vzhled a značky. Funkcích nástroje Visual Studio a skupinami příkaz nabídky je možné snadno zapnout zapnout a vypnout. Aplikační tituly, ikony aplikace a úvodní obrazovky jsou plně přizpůsobit. Seznam přizpůsobitelné funkce najdete v tématu [přizpůsobení izolované prostředí](../extensibility/customizing-the-isolated-shell.md).  
  
 Pro práci s projektem izolované prostředí, je nutné nainstalovat sadu Visual Studio SDK. Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
 Pokud chcete vytvořit aplikaci izolované prostředí, začněte projekt sady Visual Studio Shell izolované. Tento projekt obsahuje vše potřebné pro vývoj a testování aplikace izolované prostředí. Jakmile budete připraveni k zápisu instalačního programu, která nasadí aplikaci, musíte získat izolované prostředí redistribuovatelného balíčku z [redistribuovatelný balíček Microsoft Visual Studio Shell (Izolovaná)](http://go.microsoft.com/fwlink/?LinkId=616022).  
  
> [!NOTE]
>  Než se dostanete k redistribuovatelného balíčku izolované prostředí, vyzve k vyplnění přehled stručný zákazníků.  Po vyplnění průzkumu, budete přesměrováni na stránku s odkazy na stažení redistribuovatelný balíček Visual Studio připojení.  Můžete najít odkazy stažení při dalších návštěvách k webu Visual Studio připojení v části **programy &#124; PROSTŘEDÍ VISUAL STUDIO 2015 integrované a IZOLOVANÉ** kartě.  
  
> [!NOTE]
>  Další informace o tom, jak nasadit aplikaci izolované založený na prostředí najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
## <a name="working-with-the-isolated-shell"></a>Práce s izolované prostředí  
 Aplikace z Visual Studia, které jsou izolované prostředí má úplný přístup ke službám Visual Studio a podporuje speciální přizpůsobení a značka. Izolované prostředí aplikace můžete přizpůsobit několika způsoby:  
  
-   Součásti VSPackages a Managed Extensibility Framework (MEF) můžete použít k rozšíření aplikace izolované prostředí, stejně jako, kterou použijete v jiné rozšíření sady Visual Studio. Další informace najdete v tématu [rozšíření izolované prostředí](../extensibility/extending-the-isolated-shell.md).  
  
-   Chcete-li funkcích nástroje Visual Studio a skupinami příkaz nabídky k dispozici nebo není k dispozici, aktualizujte soubor .vsct v projektu uživatelské rozhraní (UI) aplikace.  
  
-   Chcete-li odebrat **možnosti** stránky ani jiné součásti prostředí sady Visual Studio z aplikace, aktualizujte soubor .pkgundef aplikace.  
  
-   Pokud chcete upravit chování prostředí nebo jiných aspektů zobrazení, aktualizujte soubor .pkgdef aplikace.  
  
-   Některé aspekty prostředí lze zadat také při spuštění aplikace. K tomuto účelu aktualizujte parametry ve volání počáteční vstupní bod appenvstub.dll.  
  
 Další informace o různých prvků, které můžete přizpůsobit, najdete v části [elementy izolované prostředí](../extensibility/elements-of-the-isolated-shell.md).  
  
## <a name="standard-features-of-the-isolated-shell"></a>Standardní funkce izolované prostředí  
 Následující funkce jsou standardní na všechny edice sady Visual Studio.  
  
|Funkce kategorie|Funkce|  
|----------------------|-------------|  
|Funkce rozhraní IDE|Import a Export nastavení<br /><br /> Instalační program sady nástrojů ovládací prvek<br /><br /> Seznam úkolů & Seznam chyb<br /><br /> Okno Výstup<br /><br /> Úvodní stránka<br /><br /> Okno vlastností<br /><br /> Sada nástrojů<br /><br /> Průzkumník řešení<br /><br /> BOOKMARK – okno<br /><br /> zobrazení tříd<br /><br /> prohlížeč objektů<br /><br /> Příkazové okno<br /><br /> Osnova dokumentu<br /><br /> Zobrazení prostředků<br /><br /> Externí nástroje<br /><br /> Přidat odkaz na službu Windows Communication Foundation (WCF)<br /><br /> Jazyk integrovaná podpora dotazu (LINQ)|  
|Editor nebo návrháře|Kód procházení nástroje (jednotné najít, definice zdroje, dědičnost)<br /><br /> IntelliSense<br /><br /> Inteligentní značky<br /><br /> Správce fragmentů kódu<br /><br /> Fragmenty kódu<br /><br /> Refaktoring<br /><br /> Velmi výpis<br /><br /> Filtrování IntelliSense<br /><br /> Definice kódu – okno<br /><br /> Návrhář aplikace<br /><br /> Návrhář formulářů Windows<br /><br /> Návrhář Windows Presentation Foundation (WPF)|  
|Ladění|Vyhodnocovací filtr výrazů jazyka C#<br /><br /> Místní ladění<br /><br /> Spravované ladění<br /><br /> Upravit a pokračovat<br /><br /> Ladění mezi vlákny<br /><br /> Vizualizace<br /><br /> DataTips<br /><br /> Nativní ladění<br /><br /> Ladění skriptu<br /><br /> Spolupráce ladění<br /><br /> Ladění v běhu (JIT)<br /><br /> Ladění více procesů<br /><br /> Ladění XSLT<br /><br /> Připojení k místní proces<br /><br /> Body trasování<br /><br /> Breakpoint – omezení|  
|Data|V Průzkumníku serveru (zjednodušená - pouze Data)<br /><br /> Datové vazby k místním datům (. MDF nebo. MDB)<br /><br /> Datové vazby k objektu<br /><br /> Datové vazby k webové službě<br /><br /> Úplnou sadu dat ovládacích prvků<br /><br /> XML editor<br /><br /> Vazbě dat na serveru místní databáze<br /><br /> okno Zdroje dat|  
|Web|Editor HTML<br /><br /> Webový prohlížeč<br /><br /> Návrhář webových formulářů<br /><br /> Webový projekt<br /><br /> Projekt webové aplikace|  
|Rozšiřitelnost|Využívá VSPackages a MEF komponenty|  
  
## <a name="see-also"></a>Viz také  
 [Prostředí shell (izolovaný nebo integrované)](../extensibility/shell-isolated-or-integrated.md)