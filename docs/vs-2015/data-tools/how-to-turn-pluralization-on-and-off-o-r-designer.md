---
title: 'Postupy: vypnutí pluralizace a zapnutí (O R Designer) | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 02fa8b50b28f967a0835f68e85d146ca1eea514b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682062"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>Postupy: vypnutí pluralizace a zapnutí (O/R Designer)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postup: zapnutí a vypnutí (O R Designer) pluralizace](https://docs.microsoft.com/visualstudio/data-tools/how-to-turn-pluralization-on-and-off-o-r-designer).  
  
  
Ve výchozím nastavení se při přetažení databázových objektů, které mají jména končící na s nebo dokumentu z **Průzkumníka serveru**/**Průzkumník databáze** na [LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md), názvy generovaných tříd entit se změnil z množném čísle k jednotném čísle. To slouží k reprezentaci přesněji skutečnost, že třída vytvořenou instanci entity se mapuje na jeden záznam dat. Příkladem je přidání tabulky Zákazníci [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] výsledky v třídu entity s názvem zákazníka, protože třída bude obsahovat data pro jediného zákazníka.  
  
> [!NOTE]
>  Pluralizace je ve výchozím pouze v anglické jazykové verzi sady Visual Studio.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-turn-pluralization-on-and-off"></a>K zapnutí a vypnutí pluralizace  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  V **možnosti** dialogového okna rozbalte **databázové nástroje**.  
  
> [!NOTE]
>  Vyberte **zobrazit všechna nastavení** Pokud **databázové nástroje** uzel není viditelný.  
  
1.  Klikněte na tlačítko **O/R Designer**.  
  
2.  Nastavte **Pluralizaci názvů** k **povoleno** = **False** nastavit [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] tak, aby neměnil názvy tříd.  
  
3.  Nastavte **Pluralizaci názvů** k **povoleno** = **True** použít pluralizace pravidla pro názvy tříd objektů, které jsou přidány do [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
## <a name="see-also"></a>Viz také  
 [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [Technologie LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)

