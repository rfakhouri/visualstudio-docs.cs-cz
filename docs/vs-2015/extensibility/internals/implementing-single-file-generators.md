---
title: Implementace generátorů tvořených jedním souborem | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom tools, implementing
- projects [Visual Studio SDK], extensibility
- projects [Visual Studio SDK], managed custom tools
ms.assetid: fe9ef6b6-4690-4c2c-872c-301c980d17fe
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 30294f901f3e0536caeb84dc55af5630db24956a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631373"
---
# <a name="implementing-single-file-generators"></a>Implementace generátorů tvořených jedním souborem
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [implementace generátorů tvořených jedním souborem](https://docs.microsoft.com/visualstudio/extensibility/internals/implementing-single-file-generators).  
  
Vlastní nástroj – někdy označovány jako generátor tvořený jedním souborem – je možné rozšířit [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] a [!INCLUDE[csprcs](../../includes/csprcs-md.md)] systémy v projektů [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Vlastní nástroj je komponenta modelu COM, který implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní. Pomocí tohoto rozhraní, transformuje vlastní nástroj jeden vstupní soubor do jednoho výstupního souboru. Výsledek transformace může být zdrojový kód nebo jakýkoli jiný výstup, který je užitečný. Dva příklady souborů vlastní nástroj vygeneruje kód se kód vygeneruje v reakci na změny vizuálního návrháře a soubory vygenerované pomocí webové služby WSDL (Description Language).  
  
 Když je načtena vlastní nástroj nebo vstupní soubor je uložen, projektový systém volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> metody a předává odkazem na <xref:Microsoft.VisualStudio.Shell.Interop.IVsGeneratorProgress> rozhraní zpětného volání, které nástroj sestavy průběh uživateli.  
  
 Vlastní nástroj vygeneruje výstupní soubor je přidána do projektu se závislostí na vstupní soubor. Systém projektu automaticky určuje název výstupního souboru, na základě řetězce vrácené provádění vlastní nástroj <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>.  
  
 Musíte implementovat vlastní nástroj <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní. Volitelně podpora vlastních nástrojů <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite> rozhraní pro načtení informací ze zdroje než vstupní soubor. V každém případě před použitím vlastní nástroj, je nutné ho zaregistrovat pomocí systému nebo v [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] místního registru. Další informace o registraci vlastních nástrojů najdete v tématu [registrace generátorů tvořených jedním souborem](../../extensibility/internals/registering-single-file-generators.md).  
  
## <a name="see-also"></a>Viz také  
 [Určení výchozí Namespace projektu](../../misc/determining-the-default-namespace-of-a-project.md)   
 [Zveřejnění typů pro vizuální návrháře](../../extensibility/internals/exposing-types-to-visual-designers.md)

