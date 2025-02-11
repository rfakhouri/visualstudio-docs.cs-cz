---
title: Otevření a uložení položek projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], file persistence
- files [Visual Studio], opening and saving
- editors [Visual Studio SDK], file persistence
ms.assetid: f71898ad-335f-4c43-a177-4da87078afd1
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c406e66b1008f0bb2aad95a427e1329d4269f1f6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68158063"
---
# <a name="opening-and-saving-project-items"></a>Otevření a uložení položek projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Když přidáte nový typ projektu, musíte spravovat otevírání a ukládání souborů v projektech [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] integrované vývojové prostředí (IDE). Následující témata popisují různé přístupy k otevírání a ukládání souborů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Zobrazení souborů pomocí příkazu Otevřít soubor](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)  
 Poskytuje podrobné vysvětlení způsobu, jakým zpracovává integrovaného vývojového prostředí **otevřít soubor** příkazu a roli projektů při reagování na tento příkaz.  
  
 [Zobrazení souborů pomocí příkazu Otevřít v aplikaci](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)  
 Poskytuje podrobné vysvětlení způsobu, jakým zpracovává integrovaného vývojového prostředí **otevřít v** příkaz dotazování otevření souboru, který má některé volba standardních editorů.  
  
 [Postupy: Otevření editorů pro konkrétní projekt](../../extensibility/how-to-open-project-specific-editors.md)  
 Obsahuje podrobné pokyny pro určení, že soubory určitého typu ve vašem projektu by měla otevřít pomocí editoru specifické pro projekt.  
  
 [Postupy: Otevření standardních editorů](../../extensibility/how-to-open-standard-editors.md)  
 Obsahuje podrobné pokyny pro zadání povolení integrovaného vývojového prostředí otevřete standardní editor pro soubory ve vašem typu projektu.  
  
 [Postupy: Otevření editorů pro otevřené dokumenty](../../extensibility/how-to-open-editors-for-open-documents.md)  
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
