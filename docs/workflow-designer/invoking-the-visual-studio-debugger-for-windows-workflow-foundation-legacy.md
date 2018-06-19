---
title: Návrhář postupu provádění – vyvolání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé)
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- stepping
- Step Over command
- stepping, commands
- debugging, using workflow debugger
- workflows, debugger
- workflow debugger, starting
- Step In command
- debugger, workflow
- Step Out command
- debugging workflows, starting the debugger
ms.assetid: d6f58e35-5cce-4ff2-9afc-b2d9d0f819cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a326f8b6dc482c2adfc2caba797c38094a99f8c5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976416"
---
# <a name="invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Vyvolání ladicího programu sady Visual Studio pro Windows Workflow Foundation (zastaralé)

Toto téma popisuje, jak používat Visual Studio Debugger ladit aplikace Windows Workflow Foundation (WF) v Návrháři pracovních postupů starší verze systému Windows. Pokud budete potřebovat cílit na rozhraní .NET Framework verze 3.5 nebo WinFX, použijte starší verzi návrháře pracovních postupů.

Obecně platí při ladění starší verze pracovních postupů, stejně jako při ladění programy vytvořené v jiné sadě Visual Studio programovací jazyky. Visual Studio ladicí program pro Windows Workflow Foundation můžete spustit těmito způsoby:

-   Vyberte **připojit k procesu** na **ladění** nabídce vyberte z dostupných procesy spuštěné instance pracovního postupu.

-   Stiskněte klávesu **F5** spustit instance pracovního postupu nebo chcete-li pokračovat, aby po zarážku narazil spustila.

## <a name="stepping-through-code"></a>Procházení kódu

Ladicí program podporuje jeden z nejčastějších ladění postupů krokování s, který provádí jeden řádek kódu v čase. Existují tři příkazy pro procházení kódu:

-   **Krok v**: můžete krok do aktivity pomocí **F11**. Ladicí program do jakékoli obslužná rutina, která je definována. Pokud je definována žádná obslužná rutina, krok přes aktivity nebo složený aktivitami, které obsahují další aktivity, krok do první provádění aktivity. Zanoříte se do obslužné rutiny kód z Návrháře není podporována pro následující činnosti: **IfElseActivity**, **aktivita typu WhileActivity**, **skupiny ConditionedActivityGroup**, nebo **ReplicatorActivity**. Chcete-li ladit obslužné rutiny související s tyto aktivity, musíte umístit explicitní zarážky v kódu.

-   **Krokovat s Vystoupením**: můžete krok mimo aktivity pomocí **Shift F11**. Krokování s mimo aktivitu spouští aktuální aktivita a její na stejné úrovni aktivity dokončen. Ladicí program pak dělí na nadřazené aktuální aktivity. Když zanoříte z obslužnou rutinu kódu, ladicího programu dělí na aktivitu, ke kterému je přiřazeno obslužná rutina.

-   **Krokovat s přeskočením**: můžete krok přes aktivity pomocí **F10**. Když krokování přes složených aktivit. ladicí program dělí na prvním podřízeným objektem spustitelné složené aktivity. Když krokování přes jiný složené, například **CodeActivity** aktivity, ladicí program spustí aktivita a její přidružené obslužné rutiny a zalomení na další aktivitu. Pokud aktivita, která se spustí poslední podřízené aktivity ve složených aktivit, pak po spuštění, ladicího programu dělí na nadřazené aktivity.

## <a name="attaching-to-a-process"></a>Připojení k procesu
 K ladění připojením procesu pracovního postupu, vyberte dostupné proces z **dostupné procesy** pole se seznamem v **připojit k procesu** dialogové okno. Pokud **automatické: kód pracovního postupu** se nezobrazí v **připojit k** textové pole a pak klikněte na **vyberte**. V **vybrat typ kódu** dialogové okno, klikněte na tlačítko **ladění tyto typy kódu** a vyberte **pracovního postupu**. Pak klikněte na tlačítko **OK** a klikněte na tlačítko **Attach**.

## <a name="debugging-with-f5"></a>Ladění pomocí F5
 Pokud aplikace hostitele pracovního postupu a pracovní postup DLL jsou umístěny v různých projektů sady Visual Studio, například při použití knihovny aktivit pracovních postupů, je nutné nastavit projektu knihovny DLL pracovního postupu jako spouštěný projekt řešení sady Visual Studio k ladění pracovního postupu pomocí **F5**. Musíte taky nastavit cestu k aplikaci hostitele v projektu knihovny DLL pracovního postupu **počáteční vnějšímu programu** vlastnost.

 Pokud chcete nastavit spouštěný projekt v Průzkumníku řešení, klikněte pravým tlačítkem na název projektu a vyberte **nastavit jako spouštěný projekt**. Nastavit cestu k hostiteli v **externí program spustit** vlastnosti, klikněte dvakrát na projektu workflow **vlastnosti** uzlu v Průzkumníku řešení a vyberte **ladění** Karta. V části **spustit akci**, vyberte **počáteční vnějšímu programu** a zadejte cestu k souboru .exe, který je hostitelem pracovního postupu, kterou chcete ladit.

 Pokud hostitelskou aplikaci je nastavit jako spouštěný projekt, jenom ladicího programu sady Visual Studio je volána pro ladění. Visual Studio ladicí program pro Windows Workflow Foundation není vyvolána. Pokud se používá ladicího programu sady Visual Studio, se setkají pouze jazyka C# nebo zarážky kód jazyka Visual Basic; nastavit v Návrháři pracovních postupů nejsou zarážky. Například zarážky nastavený na <xref:System.Workflow.Activities.ParallelActivity> aktivity v návrháři se průchodu, pokud se používá Visual Studio Debugger pro Windows Workflow Foundation, ale ne v případě, že používáte ladicího programu sady Visual Studio.

## <a name="see-also"></a>Viz také

- [Postupy: Nastavení zarážek v pracovních postupech (starší verze)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)
- [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)