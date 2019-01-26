---
title: Otevření a uložení položek projektu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], file persistence
- files [Visual Studio], opening and saving
- editors [Visual Studio SDK], file persistence
ms.assetid: f71898ad-335f-4c43-a177-4da87078afd1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 58a7c9cae59bc5a02dcca53afb66c234012e6713
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54918678"
---
# <a name="opening-and-saving-project-items"></a>Otevření a uložení položek projektu
Když přidáte nový typ projektu, musíte spravovat otevírání a ukládání souborů v projektech [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE). Následující témata popisují různé přístupy k otevírání a ukládání souborů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Zobrazení souborů pomocí příkazu Otevřít soubor](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)  
 Poskytuje podrobné vysvětlení způsobu, jakým zpracovává integrovaného vývojového prostředí **otevřít soubor** příkazu a roli projektů při reagování na tento příkaz.  
  
 [Zobrazení souborů pomocí příkazu Otevřít v aplikaci](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)  
 Poskytuje podrobné vysvětlení způsobu, jakým zpracovává integrovaného vývojového prostředí **otevřít v** příkaz dotazování otevření souboru, který má některé volba standardních editorů.  
  
 [Postupy: Otevřít editoru pro konkrétní projekt](../../extensibility/how-to-open-project-specific-editors.md)  
 Obsahuje podrobné pokyny pro určení, že soubory určitého typu ve vašem projektu by měla otevřít pomocí editoru specifické pro projekt.  
  
 [Postupy: Otevřít standardních editorů](../../extensibility/how-to-open-standard-editors.md)  
 Obsahuje podrobné pokyny pro zadání povolení integrovaného vývojového prostředí otevřete standardní editor pro soubory ve vašem typu projektu.  
  
 [Postupy: Otevřít editorů pro otevřené dokumenty](../../extensibility/how-to-open-editors-for-open-documents.md)  
 Obsahuje podrobné pokyny k otevření editoru specifické pro projekt pro otevření souboru.  
  
 [Uložení standardního dokumentu](../../extensibility/internals/saving-a-standard-document.md)  
 Poskytuje podrobné vysvětlení způsobu, jakým zpracovává integrovaného vývojového prostředí **Uložit**, **uložit jako**, a **Uložit vše** příkazy pro dokument otevřen v standardní editor.  
  
 [Uložení vlastního dokumentu](../../extensibility/internals/saving-a-custom-document.md)  
 Obsahuje diagram a podrobné vysvětlení způsobu, jakým zpracovává integrovaného vývojového prostředí **Uložit**, **uložit jako**, a **Uložit vše** otevřené příkazy pro dokumenty ve vlastním editoru.  
  
 [Určení editoru, který otevře soubor v projektu](../../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)  
 Tento článek popisuje proces, který následuje integrovaného vývojového prostředí a vyberte příslušnou editoru nebo návrháře pro soubor.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytváření vlastních editorů a návrhářů](../../extensibility/creating-custom-editors-and-designers.md)  
 Jsou uvedeny čtyři typy editorů, rozhraní IDE může být hostitelem a poskytuje popisy jednotlivých editoru.  
  
 [Typy projektů](../../extensibility/internals/project-types.md)  
 Tento článek popisuje, jak řídit projekty tak, že kód je zkompilován a sestaven, způsobu otevírání editory a formátování položek projektu.