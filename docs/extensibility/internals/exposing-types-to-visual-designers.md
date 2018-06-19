---
title: Vystavení typy vizuální nástroje | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- types [Visual Studio SDK], exposing to visual designers
- designers [Visual Studio SDK], exposing types
- custom tools, exposing types to visual designers
ms.assetid: a7a32ad4-3a0a-4eb8-a6ac-491c42885639
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 28dcc17c74a5b5ef3c9784fafe972beb6f170d90
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135971"
---
# <a name="exposing-types-to-visual-designers"></a>Vystavení typy vizuální nástroje
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] aby bylo možné zobrazit vizuálního návrháře musí mít přístup k definice tříd a typů v době návrhu. Třídy jsou načteny z předdefinovanou sadu sestavení, které obsahují sadu dokončení závislostí v aktuálním projektu (odkazy a jejich závislosti). Může být také nutné pro vizuální nástroje přístup tříd a typů, které jsou definovány v soubory generované vlastních nástrojů.  
  
 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] a [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] projektu systémy poskytují podporu pro přístup k generované třídy a typů prostřednictvím dočasné přenositelností spustitelné soubory (dočasný PEs). Všechny soubory generované vlastní nástroj mohou být zkompilovány do dočasné sestavení tak, aby typy může načíst z těchto sestavení a viditelné na Designer. Výstup každé vlastní nástroj je zkompilovat do samostatné dočasné PE a úspěch nebo neúspěch toto dočasný kompilace závisí pouze na tom, zda mohou být zkompilovány vygenerovaný soubor. I když na projekt nemusí pracovat jako celek, mohou jednotlivé dočasné PEs stále k dispozici pro Designer.  
  
 Systém projektu plně podporuje pro sledování změn do výstupního souboru vlastní nástroje, za předpokladu, že tyto změny jsou výsledkem spuštění vlastního nástroje. Při každém spuštění vlastního nástroje se vygeneruje nové dočasné PE a příslušné oznámení se odesílají do Designer.  
  
> [!NOTE]
>  Protože dočasných generování spustitelný soubor se odehrává na pozadí, žádné chyby jsou hlášeny uživateli, pokud kompilace se nezdaří.  
  
 Vlastní nástroje, které využít dočasné podporu PE musí splňovat následující pravidla:  
  
-   `GeneratesDesignTimeSource` musí být nastavena na hodnotu 1 v registru.  
  
     Spustitelný soubor kompilace žádné program probíhá bez tohoto nastavení.  
  
-   Generovaný kód musí být ve stejném jazyce jako globální projektu nastavení.  
  
     Kompiluje dočasné PE bez ohledu na to, co nástroj vlastní sestavy jako požadované rozšíření v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> za předpokladu, že `GeneratesDesignTimeSource` 1 je nastavena v registru. Rozšíření nemusí být VB, .cs nebo .jsl; může být jakékoli rozšíření.  
  
-   Kód vygenerovaný vlastní nástroj musí být platná a musí zkompilovat na svůj vlastní pomocí sady odkazy, které se nacházejí v projektu v době <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> dokončí provádění.  
  
     Při kompilaci dočasné PE pouze zdrojový soubor zadané pro kompilátor je výstup vlastního nástroje. Vlastní nástroj, který používá dočasné PE proto musíte vygenerovat výstupní soubory, které mohou být zkompilovány nezávisle na další soubory v projektu.  
  
## <a name="see-also"></a>Viz také  
 [Úvod k objektu Správce BuildManager](http://msdn.microsoft.com/en-us/50080ec2-c1c9-412c-98ef-18d7f895e7fa)   
 [Implementace generátory jedním souborem](../../extensibility/internals/implementing-single-file-generators.md)   
 [Registrace generátorů tvořených jedním souborem](../../extensibility/internals/registering-single-file-generators.md)