---
title: 'Postupy: Poskytování podpory skrytého textu ve službě starší verze jazyka | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- hidden text, supporting
- editors [Visual Studio SDK], hidden text
- language services, implementing hidden text regions
ms.assetid: 1c1dce9f-bbe2-4fc3-a736-5f78a237f4cc
caps.latest.revision: 22
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 82b8ae72fec0d13eb9da9226945d9a55b60ce186
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63436156"
---
# <a name="how-to-provide-hidden-text-support-in-a-legacy-language-service"></a>Postupy: Poskytování podpory skrytého textu ve službě starší verze jazyka
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Můžete vytvořit skrytý text oblastech kromě oblasti osnovy. Oblasti skrytého textu může být spravovanými klienta nebo řídit editoru a umožňují zcela skrýt oblast textu. Editor zobrazí počet skrytých oblastí: jako vodorovné čáry. Příkladem je zobrazení pouze pro skript v editoru jazyka HTML.  
  
## <a name="procedure"></a>Postup  
  
#### <a name="to-implement-a-hidden-text-region"></a>K implementaci oblasti skrytého textu  
  
1. Volání `QueryService` pro <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>.  
  
     Vrátí ukazatel na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>.  
  
2. Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.GetHiddenTextSession%2A>a předejte ukazatele pro dané textové vyrovnávací paměti. Určuje, zda relace skrytého textu, který je již existuje pro vyrovnávací paměť.  
  
3. Pokud už existuje a není potřeba vytvořit jeden a ukazatel na existující <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> je vrácen objekt. Použijte tento ukazatel na výčet a nabídnout vytvořit oblasti skrytého textu. V opačném případě volat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager.CreateHiddenTextSession%2A> vytvořte relaci skrytého textu pro vyrovnávací paměť.  
  
     Ukazatel <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> je vrácen objekt.  
  
    > [!NOTE]
    > Při volání `CreateHiddenTextSession`, můžete zadat klienta skrytého textu (to znamená <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextClient>). Klient skrytého textu vás upozorní, když skrytého textu nebo osnovy rozbalená nebo sbalená uživatelem.  
  
4. Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A> můžete přidat jednu nebo více nových popisují oblastí najednou, zadáním následujících informací v `reHidReg` (<xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion>) parametru:  
  
    1. Zadejte hodnotu `hrtConcealed` v `iType` člena <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> struktury k označení, že při vytváření skrytých oblastí, nikoli na oblast osnovy.  
  
        > [!NOTE]
        > Pokud se skryté oblasti jsou skryté, editoru automaticky zobrazí čáry kolem skryté regiony udávajících přítomnost.  
  
    2. Určete, zda je oblast spravovanými klienta nebo editor spravovanými v `dwBehavior` členy <xref:Microsoft.VisualStudio.TextManager.Interop.NewHiddenRegion> struktury. Inteligentní sbalování implementace může obsahovat kombinaci řídit editoru a klient osnovy a skrytý text oblastech.
