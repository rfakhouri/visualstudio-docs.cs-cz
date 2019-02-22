---
title: 'Postupy: Přidání ovládacích prvků XMLNode do dokumentů aplikace Word'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNode control, adding to documents
- controls [Office development in Visual Studio], adding to documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 08ab6ab47ff3c916b2818d9cceac1ee839939a42
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56638475"
---
# <a name="how-to-add-xmlnode-controls-to-word-documents"></a>Postupy: Přidání ovládacích prvků XMLNode do dokumentů aplikace Word
  **Důležité** informace uvedené v tomto tématu týkající se Microsoft Word je zobrazené výhradně pro výhod a užívání o jednotlivci i organizacemi, kteří se nacházejí mimo Spojené státy a jeho území nebo kteří používají nebo vývoj programy, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft před 2010 dne, kdy Microsoft odebrána implementace konkrétní funkce související s vlastní XML z aplikace Microsoft Word. Tyto informace týkající se Microsoft Word nemusí být přečteny nebo používány jednotlivcům i organizacím v USA nebo v jeho území, které používáte, nebo vývoji programů, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft po 10. ledna 2010 ; tyto produkty se chovají stejně jako produkty licenci před tímto datem nebo zakoupených a licencovaná pro použití mimo území Spojených států.

 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]

 Při namapování neopakujícími element schématu XML na dokumentu aplikace Microsoft Office Word Visual Studio automaticky přidá <xref:Microsoft.Office.Tools.Word.XMLNode> ovládacího prvku do dokumentu. Informace o mapování opakující se prvky schématu XML, naleznete v tématu [jak: Přidání ovládacích prvků XMLNodes do dokumentů aplikace Word](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md).

> [!NOTE]
>  <xref:Microsoft.Office.Tools.Word.XMLNode> Ovládací prvek není k dispozici **nástrojů** nebo **zdroje dat** časového intervalu a nelze vytvořit prostřednictvím kódu programu.

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

### <a name="to-add-an-xmlnode-control-to-a-document"></a>Chcete-li přidat ovládací prvek XMLNode do dokumentu

1.  V dokumentu v návrháři aplikace Visual Studio na pásu karet, klepněte **Developer** kartu.

    > [!NOTE]
    >  Pokud **Developer** karta není zobrazena, musíte ji nejdříve zobrazit. Další informace najdete v tématu [jak: Zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).

2.  V **XML** klikněte na možnost **schématu**.

     **Šablon a doplňků** zobrazí se dialogové okno.

3.  Klikněte na tlačítko **schématu XML** kartu.

4.  Klikněte na tlačítko **přidat schéma**.

     **Přidat schéma** zobrazí se dialogové okno.

5.  Výběr schématu XML s neopakujícími elementy schématu z **přidat schéma** dialogové okno a klikněte na tlačítko **otevřít**.

     **Schéma – nastavení** zobrazí se dialogové okno.

6.  Přiřadit alias nebo klikněte na tlačítko **OK** přidat schéma bez aliasu.

     Schéma se přidá do **přidat schéma** dialogové okno.

7.  V **přidat schéma** dialogové okno, klikněte na tlačítko **OK**.

8.  **Struktura XML** otevře se podokno úloh.

9. Klikněte na element schématu neopakujícími **struktura XML** podokna úloh se přidá do dokumentu.

     <xref:Microsoft.Office.Tools.Word.XMLNode> Ovládacího prvku je vytvořen a přidán do projektu.

## <a name="see-also"></a>Viz také:
- [XmlNode – ovládací prvek](../vsto/xmlnode-control.md)
- [Automatizace aplikace Word s použitím rozšířených objektů](../vsto/automating-word-by-using-extended-objects.md)
- [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)
- [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
