---
title: 'Postupy: Změna výstupního adresáře sestavení | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 03288cdfce66527fb48a16891e745765a72615f4
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63439262"
---
# <a name="how-to-change-the-build-output-directory"></a>Postupy: Změna výstupního adresáře sestavení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zadejte umístění výstupu na základě podle konfigurace (pro ladění, vydání nebo obojí), vygenerované váš projekt.  
  
> [!NOTE]
> Pokud máte **nastavení** projektu naleznete v poznámce na konci tohoto článku.  
  
## <a name="changing-the-build-output-directory"></a>Změna adresáře výstupu sestavení  
  
#### <a name="to-change-the-build-output-directory"></a>Změna výstupního adresáře sestavení  
  
1. V panelu nabídky zvolte **projektu**, *Appname* **vlastnosti**. Můžete také kliknout pravým tlačítkem na uzel projektu v **Průzkumníka řešení** a vyberte **vlastnosti**.  
  
2. Pokud máte projekt jazyka Visual Basic, vyberte **kompilaci** kartu. Pokud máte projekt jazyka Visual C#, vyberte **sestavení** kartu. Pokud máte projekt jazyka C++ nebo JavaScript projektu, vyberte **Obecné** kartu.  
  
3. V rozevíracího seznamu v horní části konfigurace zvolte konfiguraci, jejíž výstup souboru umístění, které chcete změnit (debug, release nebo všechny).  
  
     Vyhledejte položku výstupní cestu (**výstupní cesta sestavení** v jazyce Visual Basic **výstupní adresář** v jazyce Visual C++ **výstupní cesta** v JavaScriptu a C#). Zadejte nový výstupní adresář sestavení relativní k adresáři projektu.  
  
> [!NOTE]
> V nastavení projektu **název výstupního souboru** pole změní pouze umístění souboru Setup.exe, ne však umístění souborů projektu. Další informace najdete v tématu **sestavení, vlastnosti konfigurace, dialogové okno Vlastnosti projektu nasazení**.  
  
## <a name="see-also"></a>Viz také  
 [Stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md)   
 [Obecná stránka vlastností (projekt)](http://msdn.microsoft.com/library/593b383c-cd0f-4dcd-ad65-9ec9b4b19c45)   
 [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)
