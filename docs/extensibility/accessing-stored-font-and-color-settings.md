---
title: Přístup k uložené písma a barev nastavení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- fonts, accessing stored settings
- font and color control [Visual Studio SDK], persistence
- colors, accessing stored settings
ms.assetid: beba7174-e787-45c2-b6ff-a60f67ad4998
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1280555a2b8a293fcdd0f86891a1d198ef3c99d6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="accessing-stored-font-and-color-settings"></a>Přístup k uložené písma a barev
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Integrované vývojové prostředí (IDE) ukládá změny u nastavení písma a barev v registru. Můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> rozhraní pro přístup k tato nastavení.

## <a name="to-initiate-state-persistence-of-fonts-and-colors"></a>Chcete-li zahájit stavu trvalost písma a barev
 Písma a barev informace jsou uloženy podle kategorie v následujícím umístění registru: [HKCU\SOFTWARE\Microsoft \Visual Studio\\*\<verze sady Visual Studio >*\FontAndColors\\  *\<CategoryGUID >*], kde  *\<CategoryGUID >* je kategorie identifikátor GUID.

 Proto zahájíte trvalost VSPackage musí:

-   Získat <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> rozhraní voláním `QueryService` vůči poskytovateli globální služby.

     `QueryService` musí být volána pomocí argumentu služby ID `SID_SVsFontAndColorStorage` a argument ID rozhraní `IID_IVsFontAndColorStorage`.

-   Použití <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.OpenCategory%2A> metoda otevřete kategorii, která nastavit jako trvalý, s použitím kategorie GUID a příznak režimu jako argumenty.

     Režim, určeného `fFlags` argument, se vytvářejí na základě hodnot v <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS> výčtu. Tento režim ovládací prvky:

    -   Nastavení, která je přístupná prostřednictvím <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> rozhraní.

    -   Všechna nastavení nebo jen ta nastavení, které uživatelé změnit a který se dá načíst pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> rozhraní.

    -   Způsob šíření změny nastavení pro uživatele.

    -   Formát hodnoty barev, které se používají.

## <a name="to-use-state-persistence-of-fonts-and-colors"></a>Použití stavu trvalost písma a barev
 Zachování písma a barev zahrnuje:

-   Synchronizace nastavení IDE s nastaveními uloženými v registru.

-   Šíření informace úpravy registru.

-   Nastavení nebo načtení nastavení uložená v registru.

 Synchronizace nastavení úložiště s nastavení IDE je z velké části transparentní. Základní IDE automaticky zapisuje aktualizované nastavení pro **zobrazení položky** pro položky registru kategorií.

 Pokud více VSPackages sdílet určité kategorie, VSPackage měli vyžadovat, aby se události generují při metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> rozhraní se používají k úpravě nastavení registru uložené.

 Ve výchozím nastavení není povoleno generování událostí. Chcete-li povolit generování událostí, musí být otevřeno kategorii pomocí <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS>. Otevírání kategorii způsobí, že rozhraní IDE pro volání odpovídající <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> metodu, která implementuje VSPackage.

> [!NOTE]
>  Úpravy prostřednictvím **písma a barev** stránka vlastností generovat události, které jsou nezávislé na <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>. Můžete použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> rozhraní k určení, zda je před voláním metody třeba aktualizace mezipaměti nastavení písma a barev <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> třídy.

### <a name="storing-and-retrieving-information"></a>Ukládání a načítání informací o
 Chcete-li získat nebo nakonfigurovat informace, které uživatel může změnit pro položku s názvem zobrazení v otevřené kategorie, volejte VSPackages <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.SetItem%2A> metody.

 Informace o písma atributy pro určité kategorie se získávají pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.SetFont%2A> metody.

> [!NOTE]
>  `fFlags` Argument, který je předán <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.OpenCategory%2A> metoda při otevření této kategorie definuje chování <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A> metody. Ve výchozím nastavení tyto metody vrací jenom informace o zobrazení položek, které se změnily. Ale kategorie se při otevření pomocí <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS> příznak i aktualizovat a beze změny zobrazit položky byla přístupná pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A>.

 Ve výchozím nastavení, změnit jenom **zobrazení položky** informace jsou uchovávány v registru. <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> Rozhraní nelze použít k načtení všech nastavení pro písma a barev.

> [!NOTE]
>  <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetFont%2A> metody vrací REGDB_E_KEYMISSING (0x80040152L), když je budete používat k načtení informací o beze změny **zobrazení položky**.

 Nastavení všech **zobrazení položky** v konkrétní **kategorie** lze získat pomocí metody <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> rozhraní.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>
- <xref:Microsoft.VisualStudio.Shell.Interop.__FCSTORAGEFLAGS>
- [Implementace vlastních kategorií a zobrazit položky](../extensibility/implementing-custom-categories-and-display-items.md)