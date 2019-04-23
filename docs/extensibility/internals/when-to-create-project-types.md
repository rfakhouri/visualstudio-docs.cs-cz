---
title: Kdy vytvořit typy projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project types, conditions for creating
ms.assetid: 26adc860-ee4a-4f5c-95e1-e41b207dd7e6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eaf8982afb01ee07eb8c2d672f351c6e917620a6
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60094421"
---
# <a name="when-to-create-project-types"></a>Kdy vytvořit typy projektů
Vytváří se nový typ projektu poskytuje základ pro přizpůsobení [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] pro vaše uživatele. Ale vytváří se nový typ projektu se nevyžaduje pro všechny [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] vlastní nastavení. Následující pokyny vám měla pomoci určit, zda je nový typ projektu vyžaduje pro váš scénář.

## <a name="create-a-new-project-type"></a>Vytvořit nový typ projektu
 Pokud chcete přizpůsobit, je nutné vytvořit typ projektu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tak, aby fungoval v jedné nebo více z následujících způsobů:

- Součástí sestavení, nasazení, konfigurace a Správa zdrojového kódu.

- Nabízí podporu ladění.

- Zobrazit položky projektu v **Průzkumníka řešení**.

- Použití **otevřít projekt** nebo **nový projekt** dialogové okno.

- Vnoření projektů podpory.

## <a name="extend-an-existing-project-type"></a>Rozšířit existující typ projektu
 Můžete chtít vytvořit nový typ projektu, můžete použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] následujícím způsobem upravit nebo rozšířit existující typ projektu chování, například úprava procesu sestavení pro [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] projekty:

- Pracovat s více soubory jako jeden celek.

- Zobrazte jeden soubor jako hierarchii podřízené položky.

- Zobrazte příkaz kontextu kolem editory.

- Zobrazte kontext služby pro editory.

## <a name="use-an-existing-project-type"></a>Použít existující typ projektu
 Vytvoření nového projektu je někdy nezbytné. V následující tabulce jsou uvedeny úlohy, které nemají typ projektu pro vytvoření.

|Úloha|Popis|
|----------|-----------------|
|Zpracování příkazů|Žádné VSPackage dokáže zpracovat příkazy.|
|Vytváření editoru|Lze registrovat vlastních editorech. Další informace najdete v tématu [dokumentu Windows a editory](https://msdn.microsoft.com/library/603625e1-62b6-413a-bc44-089346e166bc).|
|Vlastnící systému windows|Můžete vytvořit oken nástrojů a dokumentu bez přidání nového typu projektu.|
|Vystavení vlastností v okně Vlastnosti|Všechny objekty mohou vystavit vlastnosti.|

## <a name="create-a-project-subtype"></a>Vytvoření projektu podtyp
 Podtypy projektů můžete použít k rozšíření typu spravovaný projekt bez nutnosti vytvářet nový typ projektu. Podtypy projektů použití agregace modelu COM pro rozšíření spravovaných projektů, které jsou napsané v Microsoft [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] nebo [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]. S průběhem modelu COM můžete znovu použít řadu implementace systému spravovaný projekt a však přizpůsobit pro konkrétní scénář prostřednictvím shromažďování a použití podporující rozhraní. Další informace o podtypů projektů, naleznete v tématu [podtypů projektů](../../extensibility/internals/project-subtypes.md).

## <a name="see-also"></a>Viz také
- [Dokument Windows a editory](https://msdn.microsoft.com/library/603625e1-62b6-413a-bc44-089346e166bc)
- [Kontrolní seznam: Vytvoření nových typů projektů](../../extensibility/internals/checklist-creating-new-project-types.md)
- [Hierarchie v sadě Visual Studio](../../extensibility/internals/hierarchies-in-visual-studio.md)