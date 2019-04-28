---
title: 'Postupy: Mapování schémat na dokumenty aplikace Word v sadě Visual Studio'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML schemas [Office development in Visual Studio], mapping
- mappings [Office development in Visual Studio], XML schemas to Word documents
- Word [Office development in Visual Studio], mapping XML schemas
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4c6f9ee9a7b636c6c12bfe2f8debcc05911e3b04
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441758"
---
# <a name="how-to-map-schemas-to-word-documents-inside-visual-studio"></a>Postupy: Mapování schémat na dokumenty aplikace Word v sadě Visual Studio
  **Důležité** informace uvedené v tomto tématu týkající se Microsoft Word je zobrazené výhradně pro výhod a užívání o jednotlivci i organizacemi, kteří se nacházejí mimo Spojené státy a jeho území nebo kteří používají nebo vývoj programy, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft před 2010 dne, kdy Microsoft odebrána implementace konkrétní funkce související s vlastní XML z aplikace Microsoft Word. Tyto informace týkající se Microsoft Word nemusí být přečteny nebo používány jednotlivcům i organizacím v USA nebo v jeho území, které používáte, nebo vývoji programů, které běží na produkty Microsoft Word, které byly licencovaných společností Microsoft po 10. ledna 2010 ; tyto produkty se chovají stejně jako produkty licenci před tímto datem nebo zakoupených a licencovaná pro použití mimo území Spojených států.

 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]

 Dokument je otevřen v sadě Visual Studio, můžete namapovat schématu XML k dokumentu. Můžete používat stejné nástroje Microsoft Office Word, které používáte, když je dokument otevřít mimo sadu Visual Studio. Office project vytvoří stejné objekty, zda mapování schématu pro dokument před nebo po vytvoření řešení aplikace Word.

## <a name="to-map-an-xml-schema-to-a-word-document-in-visual-studio"></a>K mapování schématu XML do dokumentů aplikace Word v sadě Visual Studio

1. Otevřete projekt dokumentu nebo šabloně aplikace Word v sadě Visual Studio.

2. Klikněte na tlačítko v dokumentu, abychom přesunutí výběru do návrháře.

3. Na pásu karet klikněte na tlačítko **Developer** kartu.

    > [!NOTE]
    > Pokud **Developer** karta není zobrazena, musíte ji nejdříve zobrazit. Další informace najdete v tématu [jak: Zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).

4. V **XML** klikněte na možnost **schématu**.

     **Šablon a doplňků** zobrazí se dialogové okno.

5. Klikněte na tlačítko **schématu XML** kartu.

6. Klikněte na tlačítko **přidat schéma**.

     **Přidat schéma** zobrazí se dialogové okno.

7. Přejděte do souboru schématu, vyberte ji a pak klikněte na tlačítko **otevřít**.

     **Schéma – nastavení** zobrazí se dialogové okno.

8. Přiřadit alias nebo klikněte na tlačítko **OK** přidat schéma bez aliasu.

9. Klikněte na **OK**.

     **Struktura XML** otevře se okno.

10. Prvky z přetáhnout **struktura XML** okno na místa v dokumentu, kde chcete vytvořit odpovídající ovládací prvky.

## <a name="see-also"></a>Viz také:
- [Postupy: Mapování schémat na listy v prostředí Visual Studio](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)
- [Schémata XML a data v přizpůsobeních na úrovni dokumentu](../vsto/xml-schemas-and-data-in-document-level-customizations.md)
