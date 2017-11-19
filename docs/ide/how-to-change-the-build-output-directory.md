---
title: "Postupy: Změna výstupního adresáře sestavení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ccbb32b9fd035a9058812eb5a3df306ff629086f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-change-the-build-output-directory"></a>Postupy: Změna výstupního adresáře sestavení
Umístění výstupu můžete zadat na základě za konfigurace (pro ladění, verzi nebo obě), vygenerovaných projektu.  
  
> [!NOTE]
>  Pokud máte **instalace** projektu viz poznámka na konci tohoto článku.  
  
## <a name="changing-the-build-output-directory"></a>Změna sestavení výstupního adresáře.  
  
#### <a name="to-change-the-build-output-directory"></a>Chcete-li změnit výstupního adresáře sestavení  
  
1.  Na řádku nabídek zvolte **projektu**, *Appname* **vlastnosti**. Můžete také kliknout pravým tlačítkem na uzel projektu v **Průzkumníku řešení** a vyberte **vlastnosti**.  
  
2.  Pokud máte projektu jazyka Visual Basic, vyberte **zkompilovat** kartě. Pokud máte projekt Visual C#, vyberte **sestavení** kartě. Pokud máte projektu jazyka C++ nebo projekt jazyka JavaScript, vyberte **Obecné** kartě.  
  
3.  V konfiguraci rozevírací seznam v horní části, zvolte konfiguraci, jejíž výstup chcete změnit (ladění, vydání nebo všechny) umístění souboru.  
  
     Vyhledejte položku výstupní cesta (**sestavení výstupní cesta** v jazyce Visual Basic **výstupního adresáře** v jazyce Visual C++, **výstupní cesta** v JavaScript a C#). Zadejte nové výstupního adresáře sestavení relativně k adresáři projektu.  
  
> [!NOTE]
>  V nastavení projektu **názvu výstupního souboru** pole změní jenom umístění souboru Setup.exe, ne však umístění souborů projektu. Další informace najdete v tématu **sestavení, vlastnosti konfigurace, dialogové okno Vlastnosti projektu nasazení**.  
  
## <a name="see-also"></a>Viz také  
 [Stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md)   
 [Obecná stránka vlastností (projekt)](/cpp/ide/general-property-page-project)   
 [Kompilaci a sestavování](../ide/compiling-and-building-in-visual-studio.md)