---
title: "Řešení potíží s fragmenty | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliSense Code Snippets, troubleshooting
- troubleshooting IntelliSense Code Snippets
- troubleshooting Visual Basic, IntelliSense Code Snippets
ms.assetid: 7b6dd40e-2f78-4b50-8e68-41fac1bcb81e
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 80e5ba76a54b584e5eed74f507f1fb3b81e7f89e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="troubleshooting-snippets"></a>Řešení potíží s fragmenty kódu
Problémy s IntelliSense – fragmenty kódu jsou obvykle způsobena dva problémy: poškozený fragment souboru nebo chybný obsah v souboru fragment kódu.  
  
## <a name="common-problems"></a>Běžné problémy  
  
### <a name="the-snippet-cannot-be-dragged-from-file-explorer-to-a-visual-studio-source-file"></a>Fragmentu nelze přetáhnout z Průzkumníka souborů zdrojový soubor Visual Studio  
  
-   Kód XML v souboru fragment kódu mohou být poškozené. **Editoru XML** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] problémy můžete najít ve struktuře XML.  
  
-   Soubor fragment kódu nemusí vyhovovat schéma fragment kódu. **Editoru XML** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] problémy můžete najít ve struktuře XML.  
  
### <a name="the-code-has-compiler-errors-that-are-not-highlighted"></a>Chyby kompilátoru, která zvýrazněná, není má kód  
  
-   Pravděpodobně chybí odkaz na projekt. Zkontrolujte dokumentaci o tomto fragmentu kódu. Pokud v počítači není nalezen odkaz, musíte ji nainstalovat. Vkládání fragment měli přidat do projektu všechny odkazy potřeby. Pokud fragmentu chybí referenční informace, které mohou být oznámeny creator fragment kódu za chybu.  
  
-   Proměnná může být definovaný. Nedefinované proměnné v fragment by měl mít zvýrazněná. Pokud ne, které mohou být oznámeny creator fragment kódu za chybu.  
  
## <a name="see-also"></a>Viz také  
 [Fragmenty kódu](../ide/code-snippets.md)