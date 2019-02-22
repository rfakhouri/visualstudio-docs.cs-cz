---
title: Implementace generátorů tvořených jedním souborem | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- custom tools, implementing
- projects [Visual Studio SDK], extensibility
- projects [Visual Studio SDK], managed custom tools
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ce8bca614d0af9c7b0557d5b5979797f127a47af
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604909"
---
# <a name="implementing-single-file-generators"></a>Implementace generátorů tvořených jedním souborem
Vlastní nástroj – někdy označovány jako generátor tvořený jedním souborem – je možné rozšířit [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] a [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] systémy v projektů [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Vlastní nástroj je komponenta modelu COM, který implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní. Pomocí tohoto rozhraní, transformuje vlastní nástroj jeden vstupní soubor do jednoho výstupního souboru. Výsledek transformace může být zdrojový kód nebo jakýkoli jiný výstup, který je užitečný. Dva příklady souborů vlastní nástroj vygeneruje kód se kód vygeneruje v reakci na změny vizuálního návrháře a soubory vygenerované pomocí webové služby WSDL (Description Language).

 Když je načtena vlastní nástroj nebo vstupní soubor je uložen, projektový systém volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> metody a předává odkazem na <xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> rozhraní zpětného volání, které nástroj sestavy průběh uživateli.

 Vlastní nástroj vygeneruje výstupní soubor je přidána do projektu se závislostí na vstupní soubor. Systém projektu automaticky určuje název výstupního souboru, na základě řetězce vrácené provádění vlastní nástroj <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>.

 Musíte implementovat vlastní nástroj <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní. Volitelně podpora vlastních nástrojů <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> rozhraní pro načtení informací ze zdroje než vstupní soubor. V každém případě před použitím vlastní nástroj, je nutné ho zaregistrovat pomocí systému nebo v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] místního registru. Další informace o registraci vlastních nástrojů najdete v tématu [registrace generátorů tvořených jedním souborem](../../extensibility/internals/registering-single-file-generators.md).

## <a name="see-also"></a>Viz také
- [Zveřejnění typů pro vizuální návrháře](../../extensibility/internals/exposing-types-to-visual-designers.md)