---
title: Oddělování datových sad a TableAdapters do různých projektů | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TableAdapters, n-tier applications
- n-tier applications, separating Datasets and TableAdapters
ms.assetid: f66a3940-6227-46af-a930-9177f425f4fd
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 304fa17ab036f868b8653efe64a59f68f0452723
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="separate-datasets-and-tableadapters-into-different-projects"></a>Samostatné datových sad a TableAdapters do různých projektů
Vylepšily typové datové sady, aby [TableAdapters](create-and-configure-tableadapters.md) a třídy datová sada může být generována do samostatných projektů. To umožňuje rychle samostatných aplikací vrstev a vytvářet vícevrstvé datové aplikace.  
  
Následující postup popisuje postup použití **návrháře Dataset** ke generování kódu datové sady do projektu, která je oddělená od projekt, který obsahuje generovaný kód TableAdapter.  
  
## <a name="separate-datasets-and-tableadapters"></a>Samostatné datových sad a TableAdapters  
Když oddělíte kód datové sady z TableAdapter kódu, musí být umístěny na projekt, který obsahuje kód datovou sadu v aktuálním řešení. Pokud není tento projekt v aktuálním řešení, nebudete mít k dispozici v **DataSet projekt** v seznamu **vlastnosti** okno.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-separate-the-dataset-into-a-different-project"></a>K oddělení datové sady do jiného projektu  
  
1.  Otevřete řešení, které obsahuje datové sady (.xsd soubor).  
  
    > [!NOTE]
    >  Pokud řešení neobsahuje projekt, do kterého chcete oddělit kódu datovou sadu, vytvoření projektu nebo přidat existující projekt k řešení.  
  
2.  Poklikejte na soubor typové datové sady (.xsd soubor) v **Průzkumníku řešení** otevřete datovou sadu v **návrháře Dataset**.  
  
3.  Vyberte na prázdnou oblast **návrháře Dataset**.  
  
4.  V **vlastnosti** okno, vyhledejte **DataSet projekt** uzlu.  
  
5.  V **DataSet projekt** , vyberte název projektu, do kterého chcete generovat kód datovou sadu.  
  
     Po výběru projekt, do kterého chcete generovat kód datové sady **souborem datové sady** výchozí název souboru je naplněna vlastnost. V případě potřeby můžete změnit název. Kromě toho, pokud chcete generovat kód datové sady do konkrétního adresáře, můžete nastavit **složky projektu** vlastnost na název složky.  
  
    > [!NOTE]
    >  Když oddělíte datových sad a TableAdapters (nastavením **DataSet projekt** vlastnost), nebude automaticky přesunout existující datovou sadu částečné třídy v projektu. Existující datovou sadu částečné třídy je třeba přesunout ručně dataset projekt.  
  
6.  Uložte datovou sadu.  
  
     Generování kódu datové sady do vybrané projektu v **DataSet projekt** vlastnost a **TableAdapter** se generuje kód do aktuálního projektu.  
  
Ve výchozím nastavení po oddělíte datovou sadu a TableAdapter kód, výsledkem je soubor diskrétní třídy v každém projektu. Původní projekt obsahuje soubor s názvem DatasetName.Designer.vb (nebo DatasetName.Designer.cs), který obsahuje kód TableAdapter. Projekt, který je určen v **Dataset projekt** vlastnost má soubor s názvem DatasetName.DataSet.Designer.vb (nebo DatasetName.DataSet.Designer.cs), který obsahuje kód datovou sadu.  
  
> [!NOTE]
>  K zobrazení souboru vygenerované třídy, vyberte datové sady nebo TableAdapter projektu. Potom v **Průzkumníku řešení**, vyberte **zobrazit všechny soubory**.  
  
## <a name="see-also"></a>Viz také
[Přehled vícevrstvých datových aplikací](../data-tools/n-tier-data-applications-overview.md)   
[Návod: Vytvoření víceúrovňové datové aplikace](../data-tools/walkthrough-creating-an-n-tier-data-application.md)   
[Hierarchická aktualizace](../data-tools/hierarchical-update.md)   
[Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)   
[ADO.NET](/dotnet/framework/data/adonet/index)