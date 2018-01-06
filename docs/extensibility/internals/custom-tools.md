---
title: "Vlastní nástroje | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, custom tools
- tools [Visual Studio], custom
- custom tools
ms.assetid: d669f154-9b23-48b6-b9f6-7419c8dd61a6
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7589c9a2aedf987af79689e8babccb554fbb4ccc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="custom-tools"></a>Vlastní nástroje
*Vlastní nástroje* vám umožní přidružit nástroj položku v projektu a spusťte tento nástroj vždy, když se soubor uložit. Některé vlastních nástrojů, někdy označovány jako *jedním souborem generátory*, se často používají k implementaci překladatele, které generují kód z dat a naopak. Můžete například vytvořit jeden soubor generátory [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] zdrojový kód soubory .settings a resx. Vygenerovaný zdrojový kód poskytuje silného typu přístup k datům v souborech .settings a resx. [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] typy projektů podporu vlastních nástrojů; [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] typy projektů nepodporují. Vlastní typy projektů může také podporovat vlastních nástrojů.  
  
 Jsou registrované součásti, které implementují vlastní nástroje `IVsSingleFileGenerator` rozhraní.  
  
 Vlastní nástroje jsou přidružené `ProjectItem` rozhraní objektu a jsou podobné návrháři a editory. Vlastní nástroj trvá soubor reprezentována `ProjectItem` jako vstup a zapíše nový soubor od jejichž název souboru `DefaultExtension` metoda.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Implementace generátorů tvořených jedním souborem](../../extensibility/internals/implementing-single-file-generators.md)  
 Popisuje postup použití <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní k implementaci vlastního nástroje.  
  
 [Registrace generátorů tvořených jedním souborem](../../extensibility/internals/registering-single-file-generators.md)  
 Obsahuje popis pro všechny položky registru pro vlastní nástroj.  
  
 [Zveřejnění typů pro vizuální návrháře](../../extensibility/internals/exposing-types-to-visual-designers.md)  
 Vysvětluje, jak projektu systémů poskytuje podporu pro vizuální nástroje přístupové generované třídy a typů prostřednictvím dočasné přenosné spustitelné soubory (PE).  
  
 [Trvalé uložení vlastnosti položky projektu](../../extensibility/persisting-the-property-of-a-project-item.md)  
 Ukazuje, jak se zachovat vlastnosti položky projektu, například autora zdrojový soubor, v souboru projektu.  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>  
 Poskytuje podrobnosti o <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>, který transformuje jeden vstupní soubor do jednoho výstupního souboru, který můžete zkompilovat nebo přidat do projektu.  
  
 <xref:EnvDTE.ProjectItem>  
 Vysvětluje `ProjectItem` rozhraní, což představuje položku v projektu.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>  
 Poskytuje podrobnosti o `DefaultExtension` metodu, která načte příponu názvu souboru, který je přiřazen k názvu výstupního souboru.  
  
## <a name="related-sections"></a>Související oddíly  
 [Rozšíření projektů](../../extensibility/extending-projects.md)  
 Popisuje způsob použití [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projekty a řešení pro uspořádání soubory kódu a soubory prostředků a implementaci řízení zdrojů.