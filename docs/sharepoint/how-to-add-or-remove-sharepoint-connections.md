---
title: 'Postupy: Přidání nebo odebrání připojení služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, browsing SharePoint sites
- SharePoint development in Visual Studio, SharePoint Connections
- SharePoint Connections [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 70594f8c881289bd394f33353f237bdab71c91f1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60077365"
---
# <a name="how-to-add-or-remove-sharepoint-connections"></a>Postupy: Přidání nebo odebrání připojení služby SharePoint
  Průzkumníku serveru vám umožňuje procházet servery služby SharePoint, stejně jako datová připojení. Však před můžete procházet obsah webu služby SharePoint je třeba přidat ji **připojení služby SharePoint** uzlu.

### <a name="to-add-a-sharepoint-site-to-the-sharepoint-connections-node"></a>Přidání webu služby SharePoint do uzlu připojení služby SharePoint

1. V panelu nabídky zvolte **zobrazení**, **Průzkumníka serveru**.

2. V **Průzkumníka serveru**, zvolte **připojení služby SharePoint** uzel a potom na panelu nabídek zvolte **nástroje** > **přidat SharePoint Připojení**.

3. V **přidat připojení k Sharepointu** zadejte [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] pro Sharepointový web (například http://testserver/sites/unittests).

### <a name="to-delete-a-sharepoint-site-from-the-sharepoint-connections-node"></a>Chcete-li odstranit web služby SharePoint z uzlu připojení služby SharePoint

1. V panelu nabídky zvolte **zobrazení**, **Průzkumníka serveru** otevřete **Průzkumníka serveru**.

2. Rozbalte **připojení služby SharePoint** uzlu zobrazíte webu služby SharePoint, kterou chcete odstranit z **Průzkumníka serveru**.

3. Vyberte lokalitu a pak na panelu nabídek zvolte **upravit** > **odstranit**.

    > [!NOTE]
    >  Tento krok nedojde k odstranění podkladové lokality; Odstraní pouze připojení z **Průzkumníka serveru**.

## <a name="see-also"></a>Viz také:
- [Procházet připojení služby SharePoint pomocí Průzkumníka serveru](../sharepoint/browsing-sharepoint-connections-using-server-explorer.md)
