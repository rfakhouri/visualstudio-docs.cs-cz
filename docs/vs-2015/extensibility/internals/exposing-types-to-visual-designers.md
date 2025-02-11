---
title: Zveřejnění typů pro vizuální návrhářské nástroje | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- types [Visual Studio SDK], exposing to visual designers
- designers [Visual Studio SDK], exposing types
- custom tools, exposing types to visual designers
ms.assetid: a7a32ad4-3a0a-4eb8-a6ac-491c42885639
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f4d6c0e163b751f1873fdb941e85c273dcc4fde5
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691209"
---
# <a name="exposing-types-to-visual-designers"></a>Zveřejnění typů pro vizuální návrháře
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] aby bylo možné zobrazit vizuálního návrháře musí mít přístup do definice třídy a typ v době návrhu. Tříd jsou načteny z předdefinovanou sadu sestavení, které zahrnují závislost kompletní sadu aktuální projekt (odkazy a jejich závislosti). Může být také nezbytné pro vizuální návrháře tříd pro přístup k a typy, které jsou definovány v souborech generovaných vlastních nástrojů.  
  
 [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] a [!INCLUDE[csprcs](../../includes/csprcs-md.md)] systémů projektů poskytují podporu pro přístup k generovaných tříd a typů přes dočasné přenosné spustitelné soubory (dočasný odkaz PEs). Všechny soubory generované vlastní nástroj mohou být zkompilovány do dočasného sestavení tak, aby typy mohou být načtena z těchto sestavení a vystavit návrháře. Výstup každé vlastního nástroje se zkompiluje do samostatných dočasné přenositelné Spustitelné a úspěch nebo neúspěch Tato dočasná kompilace závisí jenom na, zda je či není vygenerovaný soubor může být zkompilován. I v případě, že projekt nemusí být sestaven jako celek, mohou jednotlivé dočasný odkaz PEs stále k dispozici do návrháře.  
  
 Systém projektu obsahuje plnou podporu pro sledování změn do výstupního souboru vlastní nástroj, za předpokladu, že tyto změny jsou výsledkem spustit vlastní nástroj. Pokaždé, když je spustit vlastní nástroj, se vygeneruje nové dočasné přenositelné Spustitelné, a příslušné oznámení se odesílají do návrháře.  
  
> [!NOTE]
> Protože dočasných spustitelný generování souboru probíhá na pozadí, jsou pro uživatele hlášeny žádné chyby, pokud kompilace se nezdaří.  
  
 Vlastní nástroje, které budou využívat podporu dočasné PE musí postupovat podle následujících pravidel:  
  
- `GeneratesDesignTimeSource` musí být nastavena na hodnotu 1 v registru.  
  
     Žádná spustitelný soubor kompilace programu probíhá bez tohoto nastavení.  
  
- Generovaný kód musí být ve stejném jazyce jako nastavení globální projektu.  
  
     Dočasné přenositelné Spustitelné je kompilován bez ohledu na to, co vlastní nástroj hlásí jako požadované rozšíření v <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A> za předpokladu, že `GeneratesDesignTimeSource` je nastavená na 1 v registru. Rozšíření nemusí být .vb nebo .cs, .jsl; může být jakékoli rozšíření.  
  
- Kód vygenerovaný vlastní nástroj musí být platný, a musíte zkompilovat ve vlastní pomocí sady odkazů, které se nacházejí v projektu v době <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> dokončí provádění.  
  
     Při kompilaci dočasné přenositelné Spustitelné pouze zdrojový soubor k dispozici pro kompilátor je výstup vlastního nástroje. Vlastní nástroj, který používá dočasné přenositelné Spustitelné proto musí vygenerovat výstupní soubory, které mohou být zkompilovány nezávisle na jiné soubory v projektu.  
  
## <a name="see-also"></a>Viz také  
 [Představení objektu BuildManager](https://msdn.microsoft.com/50080ec2-c1c9-412c-98ef-18d7f895e7fa)   
 [Implementace generátorů tvořených jedním souborem](../../extensibility/internals/implementing-single-file-generators.md)   
 [Určení výchozí Namespace projektu](../../misc/determining-the-default-namespace-of-a-project.md)   
 [Registrace generátorů tvořených jedním souborem](../../extensibility/internals/registering-single-file-generators.md)
