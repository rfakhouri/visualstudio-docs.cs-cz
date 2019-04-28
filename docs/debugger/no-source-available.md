---
title: Žádný zdroj není k dispozici | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.nosource
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- No Source Code Available for the Current Location dialog box
ms.assetid: ed0732bc-4b8c-490f-adb1-af06869a2a6b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 85d1d1307a119fa23bf7ba015130ab9c7b6f69d5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62905216"
---
# <a name="no-source-available"></a>Žádný zdroj není k dispozici.
Váš projekt obsahuje zdrojový kód pro kód, který se pokoušíte zobrazit. Obvyklou příčinou je dvojitým kliknutím modul, který nemá ve zdrojovém kódu **okně zásobník volání** nebo **okno vláken**. Můžete pokračovat v ladění, ale můžete nastavovat zarážky a provádět jiné akce na tomto místě nelze použít v okně zdroje. Pokud je potřeba nastavit zarážku, použijte **okno zpětného překladu** místo.

 Na stránkách vlastností řešení můžete změnit adresáře, ve kterém se ladicí program vyhledá zdrojové soubory a zjistit, aby ladicí program ignorovat vybrané zdrojové soubory. Zobrazit [ladit zdroj souborů, společná nastavení řešení vlastnost dialogového okna stránky](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md).

 **Procházet a najít zdrojový kód** kliknutím na tento odkaz otevřete dialogové okno, kde můžou procházet zdrojový kód.

 **Zobrazit zpětný překlad** spustí **okno zpětného překladu**.

 **Vždy zobrazit zpětný překlad pro chybějící zdrojové soubory** výběr této možnosti se zobrazí **okno zpětného překladu** automaticky v při, žádný zdroj není k dispozici. Toto nastavení lze také změnit v **možnosti** dialogovém okně **ladění** kategorie, **Obecné** stránky zaškrtnutím nebo zrušením zaškrtnutí **zobrazit zpětný překlad, pokud zdroj není k dispozici**.

## <a name="see-also"></a>Viz také
- [Ladění zdrojových souborů, běžné vlastnosti, dialogové okno stránek vlastností řešení](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md)
- [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
- [SOS.dll (rozšíření ladění SOS)](/dotnet/framework/tools/sos-dll-sos-debugging-extension)