---
title: "Implementace jedním souborem generátory | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom tools, implementing
- projects [Visual Studio SDK], extensibility
- projects [Visual Studio SDK], managed custom tools
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9894666dd435dcaa110ba8af8307d7e942119bee
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="implementing-single-file-generators"></a>Implementace generátory jedním souborem
Vlastní nástroj – někdy označovány jako generátor jednoho souboru – umožňuje rozšířit [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] a [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] projektu systémy v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Vlastní nástroj je komponenty modelu COM, který implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní. Použití tohoto rozhraní, transformuje vlastní nástroj jeden vstupní soubor do jednoho výstupního souboru. Výsledek transformace může být zdrojový kód nebo jakékoliv výstup, který je užitečné. Dva příklady vlastní nástroj generuje kód souborů jsou kódu vygenerované v reakci na změny v souborech generována pomocí webové služby popis Language (WSDL) a vizuálního návrháře.  
  
 Pokud vlastní nástroj je načtena, nebo vstupní soubor zůstane uložen, systém projektu volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> metoda a obsahuje odkaz na <xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> rozhraní zpětného volání, které nástroj mohou zasílat zprávy o jejím průběhu uživateli.  
  
 Výstupního souboru, který vlastní nástroj generuje se přidá do projektu se závislostí na vstupní soubor. Systém projektu automaticky určuje název výstupního souboru, založené na řetězci vrácený implementace vlastního nástroje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>.  
  
 Musí implementovat vlastní nástroj <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní. Volitelně vlastních nástrojů podpory <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> rozhraní k načtení informací z jiných zdrojů než vstupní soubor. V každém případě před vlastní nástroj můžete použít, je nutné zaregistrovat ji pomocí systému nebo v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] místním registru. Další informace o registraci vlastních nástrojů najdete v tématu [registrace generátory jeden soubor](../../extensibility/internals/registering-single-file-generators.md).  
  
## <a name="see-also"></a>Viz také  
 [Vystavení typy vizuální nástroje](../../extensibility/internals/exposing-types-to-visual-designers.md)