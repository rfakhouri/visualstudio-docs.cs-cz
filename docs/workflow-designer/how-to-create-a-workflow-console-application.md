---
title: 'Postupy: vytvoření aplikace konzoly pracovního postupu | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 51a2eea7-921c-49f1-b358-68afc27f1ee9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: df1e97afc8dab747c308b3d4ff884810303b79ce
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-workflow-console-application"></a>Postupy: vytvoření aplikace konzoly pracovního postupu
[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] Umožňuje vytvořit pracovní postupy pro provádění systému nebo lidského procesy. Návrháři pracovních postupů Windows poskytuje návrhové ploše pro vytváření těchto pracovních postupů. [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Slouží k vytváření pracovních postupů v nástroji [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebo může být integrovaná do jiných aplikací, které opětovným hostováním návrháře.

 Toto téma popisuje postup použití [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] vytvoření pracovního postupu v konzolové aplikaci.

### <a name="to-create-a-workflow-console-application"></a>K vytvoření konzolové aplikace pracovního postupu

1.  Spustit [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)].

2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu...** .

     **Nový projekt** otevře se dialogové okno.

3.  V **nainstalovaných šablonách** podokně, vyberte **pracovního postupu** buď z **Visual C#** nebo **jazyka Visual Basic** seskupení, v závislosti na vaší jazykové předvolby.

4.  V prostředním podokně vyberte **pracovního postupu konzolové aplikace**.

5.  V **název** zadejte popisný název pro svůj projekt, aby bylo snadné identifikovat.

6.  V **umístění** zadejte adresář, ve kterém chcete uložit projektu, nebo klikněte na tlačítko **Procházet** přejděte k němu.

7.  V **řešení** pole, zadejte název nové řešení. Klikněte na tlačítko **OK** k vytvoření aplikace.

    > [!NOTE]
    > Pokud chcete přidat do existujícího řešení pracovního postupu konzolovou aplikaci, otevřete toto řešení v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], klikněte pravým tlačítkem na řešení v **Průzkumníku řešení**a vyberte **přidat**, pak **Nový projekt...** otevřete **nový projekt** dialogové okno. Pokračujte, jak je popsáno výše v tomto postupu.

8.  Šablona projektu vytvoří definici pracovního postupu v jazyce XAML a definice aplikace konzoly je ve zdrojovém kódu. [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Otevře a zobrazí se na plátno pro pracovní postup, který jste vytvořili.

9. Chcete-li vytvořit pracovní postup, přetáhněte aktivity nebo jiné položky pracovního postupu z **sada nástrojů** na návrhovou plochu do svého pracovního postupu.

## <a name="see-also"></a>Viz také

- [Vytvoření projektu pracovního postupu](../workflow-designer/creating-a-workflow-project.md)