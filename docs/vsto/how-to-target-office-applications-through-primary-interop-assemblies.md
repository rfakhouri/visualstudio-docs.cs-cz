---
title: Cílová aplikace Office primárních sestaveních vzájemné spolupráce
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- assemblies [Office development in Visual Studio], PIA references
- primary interop assemblies [Office development in Visual Studio], adding references to
- Office primary interop assemblies in Visual Studio, adding references to
- Office applications [Office development in Visual Studio], automating
- application development [Office development in Visual Studio], automating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c6e92b3b4dd46885de7f30f5364d30f39b5c2bd7
ms.sourcegitcommit: 7eb2fb21805d92f085126f3a820ac274f2216b4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2019
ms.locfileid: "67328880"
---
# <a name="how-to-target-office-applications-through-primary-interop-assemblies"></a>Postupy: Cílení na aplikace Office primárních sestaveních vzájemné spolupráce
  Když vytvoříte nový projekt sady Office, Visual Studio automaticky přidá odkazy na aplikace Microsoft Office primární sestavení interop (PIA), které jsou nezbytné k sestavení projektu. Je nutné přidat odkazy na další sestavení PIA v následujících scénářích:

- Chcete používat funkce z jiné aplikace Microsoft Office ve vašem projektu. Můžete například chtít používat funkce aplikace Microsoft Office Excel v projektu pro aplikaci Microsoft Office Word.

- Chcete automatizovat aplikace Microsoft Office, které nemají vyhrazené projekty v sadě Visual Studio, jako je například Microsoft Office Access.

  [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

  [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

## <a name="to-add-a-reference-to-a-primary-interop-assembly"></a>Chcete-li přidat odkaz na primární spolupracující sestavení

1. Otevřete si projekt Office a vyberte název projektu v **Průzkumníka řešení**.

2. Na **projektu** nabídky, klikněte na tlačítko **přidat odkaz**.

3. Na **Framework** kartu, vyberte PIA, které chcete v **název komponenty** seznamu. Další informace o dostupných primární definiční sestavení Microsoft Office, naleznete v tématu [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md).

     Pokud projekt zaměřen [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, **Embed Interop Types** pro odkaz na sestavení je nastavena na **True** ve výchozím nastavení. Pomocí tohoto nastavení vaše řešení nevyžaduje PIA v počítačích koncových uživatelů. Další informace najdete v tématu [návrhu a vytvořte řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md).

    > [!NOTE]
    > V projektech pro systém Office, vždy přidat odkazy na sestavení PIA sady Office pomocí **.NET** karty **přidat odkaz** dialogové okno místo **COM** kartu. Další informace najdete v tématu [primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md).

4. Klikněte na **OK**.

     Název sestavení se zobrazí v **odkazy** složky **Průzkumníka řešení**.

## <a name="see-also"></a>Viz také:
- [Primární spolupracující sestavení Office](../vsto/office-primary-interop-assemblies.md)
- [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)
- [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)
- [Postupy: Instalace primárních sestavení vzájemné spolupráce Office](../vsto/how-to-install-office-primary-interop-assemblies.md)
