---
title: Důležité příkazy pro jazyk služby filtry | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services, filters
- language services, commands to support
ms.assetid: 4948c494-3d4d-4f50-b3f9-959e73f90e4d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 73ecbad3578c356ed9f82f79cdf9144d4c2bd32d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66335076"
---
# <a name="important-commands-for-language-service-filters"></a>Důležité příkazy pro filtry služby jazyka
Pokud chcete vytvořit filtr služby plnohodnotný jazyk, vezměte v úvahu následující příkazy pro zpracování. Úplný seznam identifikátorů příkaz je definován v <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> výčtu pro spravovaný kód a záhlaví Stdidcmd.h soubor pro nespravované [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] kódu. Můžete najít soubor Stdidcmd.h v *cestu instalace sady Visual Studio SDK*\VisualStudioIntegration\Common\Inc.

## <a name="commands-to-handle"></a>Příkazy ke zpracování

> [!NOTE]
> Není to povinné pro filtrování pro každý příkaz v následující tabulce.

|Příkaz|Popis|
|-------------|-----------------|
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Odesílá se, když uživatel klepne pravým tlačítkem myši. Tento příkaz označuje, že je čas na místní nabídky. Pokud tento příkaz nelze zpracovat, textový editor poskytuje výchozí místní nabídka bez žádné příkazy specifické pro jazyk. Zahrnout vlastní příkazy v této nabídce, zpracování příkazu a zobrazení místní nabídky.|
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Obvykle posílají, když uživatel zadá CTRL + J. Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> metodu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> k zobrazení okna dokončování příkazu.|
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Odesílá se, když uživatel zadá znak. Sledujte tento příkaz můžete určit, kdy zadání znaku aktivační události a k poskytování příkaz dokončení, metoda tipy a text značky, třeba barevné zvýrazňování syntaxe, párování složených závorek a označování chyb. Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> metodu na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> pro dokončování příkazů a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow.SetMethodData%2A> metodu na <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow> metoda tipy. Chcete-li podporovat text značky, sledujte tento příkaz k určení, zda je zadaný znak je nutné aktualizovat vaše značky.|
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Odesílá se, když uživatel zadá klávesu Enter. Monitorovat tento příkaz určuje, kdy chcete zavřít okno tipů metoda voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> metodu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>. Ve výchozím zobrazení textu zpracovává tento příkaz.|
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Odesílá se, když uživatel zadá klávesu Backspace. Monitorování k určení toho, kdy chcete zavřít okno tipů metoda voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData.OnDismiss%2A> metodu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodData>. Ve výchozím zobrazení textu zpracovává tento příkaz.|
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Odeslané z nabídky nebo klávesovou zkratku. Volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> metodu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> okno tipů aktualizovat informace o parametru.|
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Odesílá se, když uživatel najede myší proměnné nebo se umístí kurzor na proměnnou a vybere **rychlé informace** z **IntelliSense** v **upravit** nabídky. Návratový typ proměnné v popisu voláním <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateTipWindow%2A> metodu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>. Pokud ladění je aktivní, by měl tip také zobrazí hodnotu proměnné.|
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Obvykle posílají, když uživatel zadá kombinaci kláves CTRL + MEZERNÍK. Tento příkaz zjistí, služba jazyka pro volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> metodu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>.|
|<xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID><br /><br /> <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID>|Poslané z nabídky, obvykle **Zakomentovat výběr** nebo **Odkomentovat výběr** z **Upřesnit** v **upravit** nabídky. <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> Označuje, že uživatel chce okomentujte vybraného textu. <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> označuje, že uživatel chce zrušte komentář u vybraného textu. Pouze služba jazyka je možné implementovat tyto příkazy.|

## <a name="see-also"></a>Viz také
- [Vývoj služby starší verze jazyka](../../extensibility/internals/developing-a-legacy-language-service.md)