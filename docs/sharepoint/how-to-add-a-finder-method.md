---
title: 'Postupy: Přidání vyhledávací metody | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], get entities
- Business Data Connectivity service [SharePoint development in Visual Studio], return entities
- BDC [SharePoint development in Visual Studio], return entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Finder method
- Business Data Connectivity service [SharePoint development in Visual Studio], get entities
- BDC [SharePoint development in Visual Studio], Finder method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 49f494fa2c0fb35f7d2a65dc2ccb6b6d2d761cbe
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63428730"
---
# <a name="how-to-add-a-finder-method"></a>Postupy: Přidání vyhledávací metody
  Chcete-li povolit službu Business Data Connectivity (BDC) zobrazíte seznam entit v seznamu nebo webové části, musíte vytvořit *Finder* metoda. Metoda hledání je zvláštní metoda, která vrátí kolekci instancí entity. Další informace naleznete v tématu [Model Připojení obchodních dat návrhu](../sharepoint/designing-a-business-data-connectivity-model.md).

### <a name="to-create-a-finder-method"></a>Chcete-li vytvořit metodu Finder

1. Na **návrháři služby BDC**, zvolit entitu.

    Další informace najdete v tématu [jak: Přidání entity do modelu](../sharepoint/how-to-add-an-entity-to-a-model.md).

2. V panelu nabídky zvolte **zobrazení** > **ostatní Windows** > **podrobnosti metody služby BDC**.

    **Podrobnosti metody služby BDC** otevře se okno. Další informace o **podrobnosti metody služby BDC** okna, viz [přehled nástrojů pro návrh modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).

3. V **přidat metodu** seznam, zvolte **vytvořit vyhledávací metody**.

    Visual Studio přidá metodu, návratový parametr a typ popisovače.

4. Popisovač typu nakonfigurujte jako popisovač typu kolekce entity. Další informace o tom, jak vytvořit popisovač typu kolekce entit najdete v tématu [jak: Definování deskriptoru typu pro parametr](../sharepoint/how-to-define-the-type-descriptor-of-a-parameter.md).

   > [!NOTE]
   > Není nutné tento krok provést, pokud jste přidali do entity konkrétní vyhledávací metoda. Visual Studio používá popisovač typu, který jste definovali v konkrétní vyhledávací metoda.

5. V **Průzkumníka řešení**, otevřete místní nabídku souboru služby kód, který byl vygenerován pro entitu a pak zvolte **zobrazit kód**. Další informace o souboru kód služby naleznete v tématu [vytvořit model připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).

6. Přidejte kód do metody hledání. Tento kód provede následující:

   - Načte data ze zdroje dat.

   - Vrátí seznam entit služby katalogu obchodních dat.

     Následující příklad vrátí kolekci `Contact` entity pomocí dat z ukázkové databáze AdventureWorks pro SQL Server.

   > [!NOTE]
   > Nahraďte hodnotu `ServerName` pole s názvem vašeho serveru.

    [!code-csharp[SP_BDC#2](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#2)]
    [!code-vb[SP_BDC#2](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#2)]

## <a name="see-also"></a>Viz také:
- [Přehled nástroje pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Postupy: Přidání konkrétní vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)
- [Postupy: Přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)
- [Postupy: Přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)
- [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)
- [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)
