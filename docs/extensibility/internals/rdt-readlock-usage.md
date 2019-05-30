---
title: Využití RDT_ReadLock | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- RDT_ReadLock
- visible
- RDT_EditLock
- invisible
ms.assetid: b935fc82-9d6b-4a8d-9b70-e9a5c5ad4a55
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8c11cee4c1f8c150fc8bcf42b3dbc1a193d3441a
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341360"
---
# <a name="rdtreadlock-usage"></a>Využití RDT_ReadLock

[_VSRDTFLAGS. RDT_ReadLock](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS.RDT_ReadLock>) je příznak, který obsahuje logiku pro uzamčení dokumentu v systémem dokumentu tabulky (r...), který je uvedený seznam všech dokumentů, které jsou právě otevřeny v integrovaném vývojovém prostředí sady Visual Studio. Tento příznak určuje, kdy jsou otevřené dokumenty a zda dokument je zobrazen v uživatelském rozhraní nebo pevné nezaregistroval v paměti.

Obecně platí, použijete [_VSRDTFLAGS. RDT_ReadLock](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS.RDT_ReadLock>) při je splněna jedna z následujících akcí:

- Chcete otevřít dokument transparentně a jen pro čtení, ale je ještě není vytvořeno, který <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> by vlastnit.

- Chcete uživateli výzva k uložení dokumentu, kterou jste otevřeli nezaregistroval předtím, než uživatel zobrazí v uživatelském rozhraní a pak se pokusila zavřít ho.

## <a name="how-to-manage-visible-and-invisible-documents"></a>Jak spravovat viditelné a neviditelné dokumenty

Když uživatel otevře dokument v Uživatelském rozhraní <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> vlastník dokumentu musí být stanovena a [_VSRDTFLAGS. RDT_EditLock](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS.RDT_EditLock>) musí být nastaven příznak. Pokud ne <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> vlastníka je možné navázat, pak dokument se neuloží, když uživatel klikne **Uložit vše** nebo ukončí rozhraní IDE. To znamená, že pokud je otevřený dokument nezaregistroval tam, kde je změněný v paměti a uživatel je vyzván k uložení dokumentu na vypnutí nebo uložit, pokud **Uložit vše** je vybrán, pak `RDT_ReadLock` nelze použít. Místo toho je nutné použít `RDT_EditLock` a registrovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocumentLockHolder> při [__VSREGDOCLOCKHOLDER. RDLH_WeakLockHolder](<xref:Microsoft.VisualStudio.Shell.Interop.__VSREGDOCLOCKHOLDER.RDLH_WeakLockHolder>) příznak.

## <a name="rdteditlock-and-document-modification"></a>RDT_EditLock a úpravy dokumentu

Předchozí příznak uvedených označuje, že neviditelné otevření dokumentu přinese jeho `RDT_EditLock` při otevření dokumentu uživatelem do viditelné **DocumentWindow**. V takovém případě uživateli zobrazí s **Uložit** výzvu při viditelných **DocumentWindow** je zavřený. `Microsoft.VisualStudio.Package.Automation.OAProject.CodeModel` implementace, které používají <xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager> služby zpočátku fungovat, pokud je to jenom `RDT_ReadLock` se provede, (to znamená, když dokument je otevřen nezaregistroval k analýze informací o). Později, pokud je třeba upravit dokument, pak zámek se upgraduje na slabé **RDT_EditLock**. Pokud uživatel potom otevře dokument v viditelné **DocumentWindow**, `CodeModel`společnosti slabé `RDT_EditLock` vydání.

Pokud uživatel potom jej zavře **DocumentWindow** a zvolí **ne** po zobrazení výzvy k uložení otevřít dokument, pak bude `CodeModel` implementace uvolní všechny informace v dokumentu a znovu neotevře dokument z disku neviditelné při příštím Další informace jsou nezbytné k dokumentu. Subtlety toto chování je instanci, kde uživatel otevře **DocumentWindow** neviditelné otevřeného dokumentu, změní se zavře a následně klikne **ne** po zobrazení výzvy k uložení dokumentu. V tomto případě, pokud má dokument `RDT_ReadLock`, dokument nebude ve skutečnosti byl a upravený dokument zůstanou otevřené nezaregistroval v paměti, i když se uživatel rozhodl nechcete uložit dokument.

Pokud neviditelné otevření dokumentu používá weak `RDT_EditLock`, pak bude vrácen platnost zámku, když uživatel otevře dokument viditelně a žádné další zámky. Když uživatel zavírá **DocumentWindow** a zvolí **ne** po zobrazení výzvy k uložení dokumentu, pak dokument musíte zavřít z paměti. To znamená, že neviditelné klient musí naslouchat událostem rámcový sledovat výskyt této události. Dalším vyžádáním dokumentu dokumentu musí být znovu otevřít.