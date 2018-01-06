---
title: "Postupy: podporují skrytého textu ve službě jazyk starší | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- hidden text, supporting
- editors [Visual Studio SDK], hidden text
- language services, implementing hidden text regions
ms.assetid: 1c1dce9f-bbe2-4fc3-a736-5f78a237f4cc
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 664ab99af45e8c449247c5515184293ecb1a469f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-provide-hidden-text-support-in-a-legacy-language-service"></a>Postupy: podporují skrytého textu ve službě jazyk starší verze
Můžete vytvořit skrytý text oblasti kromě outline oblasti. Oblasti skrytý text může být řízenou klienta nebo editor řízené a slouží k úplně skrýt oblast textu. Editor zobrazí skryté oblasti jako vodorovné čáry. Příkladem je zobrazení pouze skriptu v editoru HTML.  
  
## <a name="procedure"></a>Postup  
  
#### <a name="to-implement-a-hidden-text-region"></a>K implementaci oblast skrytého textu  
  
1.  Volání `QueryService` pro <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>.  
  
     Tento příkaz vrátí ukazatel na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.  
  
2.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>a předejte ukazatel pro danou textovou vyrovnávací paměť. Určuje, zda relace skrytý text, který je již existuje pro vyrovnávací paměť.  
  
3.  Pokud už existuje, pak není potřeba vytvořit jednu a ukazatel na existující <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> se vrátí objekt. Použijte tento ukazatel výčet a vytvořit skrytý text oblasti. Jinak volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> pro vytvoření relace skrytého textu pro vyrovnávací paměť.  
  
     Ukazatel <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> se vrátí objekt.  
  
    > [!NOTE]
    >  Při volání `CreateHiddenTextSession`, můžete zadat klienta skrytého textu (tj, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient>). Klient pro skrytý text vás upozorní, když skrytého textu nebo osnovy je rozbalit nebo sbalit uživatelem.  
  
4.  Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> můžete přidat jeden nebo více nových popisují oblasti současně, zadat následující informace v `reHidReg` (<xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>) parametr:  
  
    1.  Zadejte hodnotu `hrtConcealed` v `iType` členem <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> struktura indikující, že vytváříte Skrytá oblast, nikoli oblast outline.  
  
        > [!NOTE]
        >  Skryté skryté oblasti, zobrazí se v editoru automaticky čáry kolem skryté oblasti, aby naznačilo přítomnost jejich.  
  
    2.  Určete, zda je oblast řízené klienta nebo editor řídí ve službě `dwBehavior` členy <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> struktura. Inteligentní popisující implementace může obsahovat kombinaci outline řídí editoru a klienta a oblastí, skrytý text.