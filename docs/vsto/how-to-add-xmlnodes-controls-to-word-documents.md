---
title: 'Postupy: Přidání ovládacích prvků XMLNodes do dokumentů aplikace Word'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNodes control, adding to documents
- controls [Office development in Visual Studio], adding to documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9d754d7be732931cf3d50cf28db396b5040e3874
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870188"
---
# <a name="how-to-add-xmlnodes-controls-to-word-documents"></a>Postupy: Přidání ovládacích prvků XMLNodes do dokumentů aplikace Word
  **Důležité** informace uvedené v tomto tématu týkající se Microsoft Word je zobrazené výhradně pro výhod a užívání o jednotlivci i organizacemi, kteří se nacházejí mimo Spojené státy a jeho území nebo kteří používají nebo vývoj programy, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft před 2010 dne, kdy Microsoft odebrána implementace konkrétní funkce související s vlastní XML z aplikace Microsoft Word. Tyto informace týkající se Microsoft Word nemusí být přečteny nebo používány jednotlivcům i organizacím v USA nebo v jeho území, které používáte, nebo vývoji programů, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft po 10. ledna 2010 ; tyto produkty se chovají stejně jako produkty licenci před tímto datem nebo zakoupených a licencovaná pro použití mimo území Spojených států.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 Při namapování opakující se element schématu XML na dokumentu aplikace Microsoft Office Word Visual Studio automaticky přidá <xref:Microsoft.Office.Tools.Word.XMLNodes> ovládacího prvku do dokumentu.  
  
 Informace o mapování neopakujícími prvků schématu XML, naleznete v tématu [jak: Přidání ovládacích prvků XMLNode do dokumentů aplikace Word](../vsto/how-to-add-xmlnode-controls-to-word-documents.md).  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Word.XMLNodes> Ovládací prvek není k dispozici **nástrojů** nebo **zdroje dat** okna ani může být vytvořili prostřednictvím kódu programu.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-an-xmlnodes-control-to-a-document"></a>Chcete-li přidat XmlNodes – ovládací prvek do dokumentu  
  
1.  V dokumentu v návrháři aplikace Visual Studio na pásu karet, klepněte **Developer** kartu.  
  
    > [!NOTE]  
    >  Pokud **Developer** karta není zobrazena, musíte ji nejdříve zobrazit. Další informace najdete v tématu [jak: Zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
2.  V **XML** klikněte na možnost **schématu**.  
  
     **Šablon a doplňků** zobrazí se dialogové okno.  
  
3.  Klikněte na tlačítko **schématu XML** kartu.  
  
4.  Klikněte na tlačítko **přidat schéma**.  
  
     **Přidat schéma** zobrazí se dialogové okno.  
  
5.  Výběr schématu XML, který obsahuje opakující se elementy schématu a klikněte na tlačítko **otevřít**.  
  
     **Schéma – nastavení** zobrazí se dialogové okno.  
  
6.  Přiřadit alias nebo klikněte na tlačítko **OK** přidat schéma bez aliasu.  
  
     Schéma se přidá do **přidat schéma** dialogové okno.  
  
7.  V **přidat schéma** dialogové okno, klikněte na tlačítko **OK**.  
  
     **Struktura XML** otevře se podokno úloh.  
  
8.  Klikněte na opakující se element schématu **struktura XML** podokna úloh se přidá do dokumentu.  
  
     <xref:Microsoft.Office.Tools.Word.XMLNodes> Ovládacího prvku je vytvořen a přidán do projektu.  
  
## <a name="see-also"></a>Viz také:  
 [XmlNodes – ovládací prvek](../vsto/xmlnodes-control.md)   
 [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)   
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
