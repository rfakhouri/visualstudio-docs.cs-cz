---
title: Kdy vytvořit typy projektů | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project types, conditions for creating
ms.assetid: 26adc860-ee4a-4f5c-95e1-e41b207dd7e6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 732d71e09d00cd5dbaa077b8a62e240fe401540b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="when-to-create-project-types"></a>Kdy vytvořit typy projektů
Vytvoření nového projektu typu poskytuje základ pro přizpůsobení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] pro vaše uživatele. Však není pro všechny požadované vytvoření nového projektu typu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] přizpůsobení. Následující pokyny by měly pomoci při určování, zda je požadována pro váš scénář nový typ projektu.  
  
## <a name="create-a-new-project-type"></a>Vytvořte nový typ projektu  
 Pokud chcete přizpůsobit musíte vytvořit typu projektu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tak, aby fungoval v jedné nebo více z následujících způsobů:  
  
-   Účast v sestavení, nasazení, konfigurace a Správa zdrojového kódu.  
  
-   Nabízí podporu ladění.  
  
-   Zobrazit položky projektu v **Průzkumníku řešení**.  
  
-   Použití **otevřeného projektu** nebo **nový projekt** dialogové okno.  
  
-   Podpora vnoření projektu.  
  
## <a name="extend-an-existing-project-type"></a>Rozšířit existující typ projektu  
 Můžete chtít vytvořit nový typ projektu, který můžete použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] následujícími způsoby změnit nebo rozšířit chování existující typ projektu, například úprava procesu sestavení pro [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projekty:  
  
-   Pracovat s více soubory jako na jednu jednotku.  
  
-   Zobrazí jeden soubor jako hierarchie dílčí položky.  
  
-   Zobrazí příkaz kontextu kolem editory.  
  
-   Editory zobrazení kontext služby.  
  
## <a name="use-an-existing-project-type"></a>Použít existující typ projektu  
 Vytvoření nového projektu není někdy nutné. V následující tabulce jsou uvedeny úlohy, které nemají typ projektu pro vytvoření.  
  
|Úloha|Popis|  
|----------|-----------------|  
|Zpracování příkazů|Všechny VSPackage může zpracovávat příkazy.|  
|Vytváření editoru|Vlastní editory lze zaregistrovat. Další informace najdete v tématu [okna dokumentu a editory](http://msdn.microsoft.com/en-us/603625e1-62b6-413a-bc44-089346e166bc).|  
|Vlastnící windows|Nástroj i dokumentu windows můžete vytvořit bez přidání nového typu projektu.|  
|Vystavení vlastností v okně vlastností|Všechny objekty můžete zobrazit vlastnosti.|  
  
## <a name="create-a-project-subtype"></a>Vytvoření projektu podtypem  
 Podtypů projektu můžete rozšířit typu spravovaný projekt bez nutnosti vytvářet nový typ projektu. Agregace COM podtypů projektu můžete použít k rozšíření spravované projekty, které jsou napsané v Microsoft [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] nebo [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]. S průběhem COM můžete znovu použít většinu implementace systému spravovaný projekt a dál přizpůsobit pro konkrétní scénář prostřednictvím agregaci a použití podporu rozhraní. Další informace o projektu podtypů najdete v tématu [projektu podtypů](../../extensibility/internals/project-subtypes.md).  
  
## <a name="see-also"></a>Viz také  
 [Okna dokumentů a editory](http://msdn.microsoft.com/en-us/603625e1-62b6-413a-bc44-089346e166bc)   
 [Kontrolní seznam: Vytvoření nové typy projektu](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Hierarchie v sadě Visual Studio](../../extensibility/internals/hierarchies-in-visual-studio.md)