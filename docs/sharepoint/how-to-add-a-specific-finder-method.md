---
title: 'Postupy: Přidání konkrétní vyhledávací metody | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], Specific Finder
- BDC [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], get an entity
- Business Data Connectivity service [SharePoint development in Visual Studio], return an entity
- BDC [SharePoint development in Visual Studio], Specific Finder
- Business Data Connectivity service [SharePoint development in Visual Studio], get an entity
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8fdd467f2b3a06398198f6fd8452c6a548bf0872
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431272"
---
# <a name="how-to-add-a-specific-finder-method"></a>Postupy: Přidání konkrétní vyhledávací metody
  Může vrátit instanci jednu entitu tím, že vytvoříte *Specific Finder* metody. Služba obchodní Data připojení (BDC) provede metody Specific Finder, když uživatel vybere entity v obchodních dat webové části nebo externí seznam. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

### <a name="to-create-a-specific-finder-method"></a>Chcete-li vytvořit konkrétní metodu Finder

1. Na **návrháři služby BDC**, zvolit entitu.

    Informace o tom, jak přidat entitu, aby **návrháři služby BDC** v sadě Visual Studio, naleznete v tématu [jak: Přidání entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md).

2. V panelu nabídky zvolte **zobrazení** > **ostatní Windows**, **podrobnosti metody služby BDC**.

    **Podrobnosti metody služby BDC** otevře se okno. Další informace o tomto okně najdete v tématu [přehled nástrojů pro návrh modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).

3. V **přidejte metodu** klikněte na položku **vytvořit konkrétní metodu Finder**.

    Visual Studio přidá následující prvky modelu. Tyto prvky se zobrazí v **podrobnosti metody služby BDC** okna.

   - Metoda.

   - Vstupní parametr metody.

   - Návratový parametr metody.

   - Popisovač typu pro každý parametr.

   - Instance metody k metodě.

     Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

4. Otevřít Visual Studio **vlastnosti** okna.

5. Nakonfigurujte typ popisovače návratového parametru jako popisovač pro typ entity. Informace o tom, jak vytvořit popisovač typu entity, naleznete v tématu [jak: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).

   > [!NOTE]
   > Není nutné tento krok proveďte, pokud jste přidali vyhledávací metody k entitě. Visual Studio používá typ popisovače, který jste definovali v vyhledávací metody.

   > [!NOTE]
   > Pokud identifikátor pole entity typu představuje pole v databázové tabulce, který je generován automaticky, nastavte **jen pro čtení** vlastnost identifikátor pole tak, aby **True**.

6. V **podrobnosti metody** okna, vyberte instanci metody metody.

7. V **okno vlastností**, nastavte **vrátí název parametru** nastavte název návratového parametru metody. Další informace o metodu instance vlastnosti najdete v tématu [třídu MethodInstance](http://go.microsoft.com/fwlink/?LinkID=169282).

8. V **Průzkumníka řešení**, otevřete místní nabídku souboru služby kód, který byl vygenerován pro entitu a pak zvolte **zobrazit kód**.

    Soubor kódu služby entity se otevře v editoru kódu. Další informace o souboru kód služby entity, naleznete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).

9. Přidejte kód do metody Specific Finder. Tento kód provede následující:

   - Načte ze zdroje dat záznam.

   - Vrátí entity do služby BDC.

     Následující příklad vrátí kontakt z ukázkové databáze AdventureWorks pro SQL Server.

     > [!NOTE]
     > Nahraďte hodnotu `ServerName` pole s názvem vašeho serveru.

     [!code-csharp[SP_BDC#3](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#3)]

## <a name="see-also"></a>Viz také:
- [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Postupy: Přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)
- [Postupy: Přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)
- [Postupy: Přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)
- [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)
- [Přehled nástroje pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)
