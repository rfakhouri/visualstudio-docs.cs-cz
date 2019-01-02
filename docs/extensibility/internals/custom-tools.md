---
title: Vlastní nástroje | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, custom tools
- tools [Visual Studio], custom
- custom tools
ms.assetid: d669f154-9b23-48b6-b9f6-7419c8dd61a6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ce8b18ee5c1c84b8e6480ffa9f91f739796f0991
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53834409"
---
# <a name="custom-tools"></a>Vlastní nástroje
*Vlastní nástroje* vám umožní přidružit nástroj položky v projektu a spusťte tento nástroj pokaždé, když je soubor uložen. Některé vlastní nástroje, někdy označovány jako *generátorů tvořených jedním souborem*, jsou často používána k implementaci překladače, které generují kód z dat a naopak. Například vytvořit generátorů tvořených jedním souborem [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] zdrojový kód z celkového počtu *.settings* a *RESX* soubory. Generovaný zdrojový kód poskytuje silného typu přístup k datům v *.settings* a *RESX* soubory. [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] a [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] typy projektů podpory vlastního nástroje. [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] typy projektů nejsou. Vlastní typy projektů může také podporovat vlastních nástrojů.  
  
 Jsou registrované součásti, které implementují vlastní nástroje `IVsSingleFileGenerator` rozhraní.  
  
 Jsou přidružené k vlastní nástroje `ProjectItem` rozhraní objektu a jsou podobné návrháři a editory. Vlastní nástroj přebírá souboru reprezentována `ProjectItem` jako vstup a zapíše nový soubor, jehož název souboru poskytuje `DefaultExtension` metoda.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Implementace generátorů tvořených jedním souborem](../../extensibility/internals/implementing-single-file-generators.md)  
 Popisuje způsob použití <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> rozhraní za účelem implementace vlastní nástroj.  
  
 [Registrace generátorů jedním souborem](../../extensibility/internals/registering-single-file-generators.md)  
 Obsahuje popis pro všechny položky registru pro vlastní nástroj.  
  
 [Vystavení typů pro vizuální návrháře](../../extensibility/internals/exposing-types-to-visual-designers.md)  
 Vysvětluje, jak systémů projektů poskytovat podporu pro vizuální návrhářské nástroje a typy tříd pro přístup k vygenerované pomocí souborů dočasné (PE portable executable).  
  
 [Zachovat vlastnosti položky projektu](../../extensibility/persisting-the-property-of-a-project-item.md)  
 Ukazuje, jak zachovat vlastnosti položky projektu, jako je například autor zdrojového souboru, v souboru projektu.  
  
## <a name="reference"></a>Odkaz  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>  
 Poskytuje podrobnosti o <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>, který transformuje jeden vstupní soubor do jednoho výstupního souboru, který má zkompilovat nebo přidat do projektu.  
  
 <xref:EnvDTE.ProjectItem>  
 Vysvětluje, `ProjectItem` rozhraní, která představuje položku v projektu.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>  
 Poskytuje podrobnosti o `DefaultExtension` metodu, která načte příponu názvu souboru, který je uveden název výstupního souboru.  
  
## <a name="related-sections"></a>Související oddíly  
 [Rozšíření projektů](../../extensibility/extending-projects.md)  
 Popisuje způsob použití [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projekty a řešení pro uspořádání souborů s kódem a soubory prostředků a jak implementovat správy zdrojového kódu.