---
title: "Postupy: vypnutí pluralizační a zapnutí (Návrhář O-R) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 87779cb647e00c990f4f8b29907a0dc344b80f42
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>Postupy: vypnutí pluralizační a zapnutí (Návrhář relací objektů)
Ve výchozím nastavení při přetažení databázové objekty, které mají názvy končící na s nebo ho bloku z **Průzkumníka serveru**/**Průzkumník databáze** na [technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md), jsou názvy tříd generovaného entit změněn z množném čísle na jednotném čísle. Důvodem je skutečnost, že třída vytvořenou instanci entity se mapuje na jeden záznam dat přesněji představují. Například přidání zákazníkům tabulka, která se [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] má za následek třídu entity s názvem zákazníka, protože třída budou uložena data pro jednoho zákazníka.  
  
> [!NOTE]
>  Pluralizační je ve výchozím nastavení pouze v anglické jazykové verzi Visual Studia.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-turn-pluralization-on-and-off"></a>Chcete-li pluralizační zapnout a vypnout  
  
1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
2.  V **možnosti** dialogové okno, rozbalte seznam **databázové nástroje**.  
  
    > [!NOTE]
    >  Vyberte **zobrazit všechna nastavení** Pokud **databázové nástroje** uzlu není viditelná.  
  
3.  Klikněte na tlačítko **Návrhář relací objektů**.  
  
4.  Nastavit **Pluralizační názvy** k **povoleno** = **False** nastavit [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] tak, aby nedošlo k jeho změně názvy tříd.  
  
5.  Nastavit **Pluralizační názvy** k **povoleno** = **True** uplatňovat pluralizační pravidla pro názvy tříd objektů, které jsou přidány do [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].  
  
## <a name="see-also"></a>Viz také  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[Technologie LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)   
[Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)