---
title: Řešení potíží s fragmenty kódu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: troubleshooting
helpviewer_keywords:
- IntelliSense Code Snippets, troubleshooting
- troubleshooting IntelliSense Code Snippets
- troubleshooting Visual Basic, IntelliSense Code Snippets
ms.assetid: 7b6dd40e-2f78-4b50-8e68-41fac1bcb81e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dea93f5c575afc96af188ab2e92e2ee12b929549
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2018
ms.locfileid: "32064043"
---
# <a name="troubleshoot-snippets"></a>Řešení potíží s fragmenty kódu

Problémy s IntelliSense – fragmenty kódu jsou obvykle způsobena dva problémy: poškozený fragment souboru nebo chybný obsah v souboru fragment kódu.

## <a name="the-snippet-cannot-be-dragged-from-file-explorer-to-a-visual-studio-source-file"></a>Fragmentu nelze přetáhnout z Průzkumníka souborů zdrojový soubor Visual Studio

-   Kód XML v souboru fragment kódu mohou být poškozené. **Editoru XML** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] problémy můžete najít ve struktuře XML.

-   Soubor fragment kódu nemusí vyhovovat schéma fragment kódu. **Editoru XML** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] problémy můžete najít ve struktuře XML.

## <a name="the-code-has-compiler-errors-that-are-not-highlighted"></a>Chyby kompilátoru, která nejsou zvýrazněna má kód

-   Pravděpodobně chybí odkaz na projekt. Zkontrolujte dokumentaci o tomto fragmentu kódu. Pokud v počítači není nalezen odkaz, musíte ji nainstalovat. Vkládání fragment měli přidat do projektu všechny odkazy potřeby. Pokud fragmentu chybí referenční informace, které mohou být oznámeny creator fragment kódu za chybu.

-   Proměnná může být definovaný. Nedefinované proměnné v fragment by měl mít zvýrazněná. Pokud ne, které mohou být oznámeny creator fragment kódu za chybu.

## <a name="see-also"></a>Viz také

- [Fragmenty kódu](../ide/code-snippets.md)
