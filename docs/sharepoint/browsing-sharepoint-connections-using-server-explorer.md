---
title: Procházení pomocí Průzkumníku serveru připojení služby SharePoint | Dokumentace Microsoftu
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.SharePointExplorer.SharePointConnection
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
ms.openlocfilehash: 8dfde37125b78e2ff8077712321b3a19816582cf
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63387809"
---
# <a name="browse-sharepoint-connections-by-using-server-explorer"></a>Procházet připojení služby SharePoint pomocí Průzkumníka serveru
  Nyní můžete procházet místní připojení služby SharePoint v **Průzkumníka serveru**. Tímto způsobem můžete procházet součásti webu služby SharePoint ve vašem systému. Součásti webu služby SharePoint, jako je například seznam definic a typy obsahu, se zobrazí v uzlu, který je pojmenován **připojení služby SharePoint** ve stromovém zobrazení **Průzkumníka serveru**. Chcete-li zobrazit **Průzkumníka serveru**, na panelu nabídek zvolte **zobrazení** > **Průzkumníka serveru**. Kromě zobrazení součásti webu služby SharePoint, můžete odebrat položky, zobrazení jejich vlastností nebo aktualizujte zobrazení stromové struktury pomocí příkazů v místní nabídce.

> [!IMPORTANT]
> Procházení webu služby SharePoint, musíte být správcem kolekce webů služby SharePoint a spuštění sady Visual Studio jako správce místního počítače. V opačném případě se zobrazí v lokalitě **Průzkumníka serveru**, ale nelze rozbalit její uzel. Pokud chcete ověřit, zda jste správcem kolekce webů, otevřete ve webovém prohlížeči otevřete web **Akce webu** nabídce zvolte **oprávnění webu**a pak klikněte na **oprávnění: Team web** zvolte **správci kolekce webů** příkaz **spravovat** na pásu karet. Název se zobrazí v textovém poli, pokud jste správcem kolekce webů. Pokud **správci kolekce webů** příkazu se nezobrazí v spravovat skupinu na pásu karet, nejste správcem kolekce webů a je nutné získat příslušná oprávnění od správce lokality.

## <a name="server-explorer-nodes"></a>Uzly Průzkumníka serveru
 Všechny komponenty jsou ve webu služby SharePoint je reprezentována uzlu **Průzkumníka serveru** stromové zobrazení v sekci **připojení služby SharePoint**. Například výchozí Sharepointové weby obsahovat typ obsahu s názvem diskuze, který představuje typ diskuze, který se zobrazí v **diskuse** stránku webu služby SharePoint. Typ obsahu diskuse obsahuje několik polí. Chcete-li zobrazit tato pole v **Průzkumníka serveru**, rozbalte **ContentTypes** uzel a pak **diskuse** uzlu. V části se několik uzlů pole, jako je například textu, předmětu diskuze a název.

## <a name="node-shortcut-menu-commands"></a>Příkazy místní nabídky uzlu
 Každý uzel má místní nabídky, ke kterým přístup tak, že pravým tlačítkem myši uzel nebo jej vyberete a potom kliknete **Shift**+**F10** klíče. Uzel příkazy mohou zahrnovat následující:

|Název příkazu|Popis|
|------------------|-----------------|
|Aktualizovat|Aktualizuje zobrazení stromové struktury tak, aby odrážela všechny změny, které mohly nastat od posledního uzlu se zobrazují.|
|Odstranit|Odebere vybraného uzlu ve stromovém zobrazení. **Poznámka:**  Tento příkaz je povolen pouze na uvedené v části připojení služby SharePoint **připojení služby SharePoint** uzlu.|
|Vlastnosti|Zobrazí dostupné vlastnosti pro vybraný uzel v **vlastnosti** okna. Vlastnosti jsou všechny jen pro čtení, a ne každý uzel nemá vlastnosti související s ním.|
|Přidání připojení|Umožňuje určit web služby SharePoint, kterou chcete procházet. K dispozici na **připojení služby SharePoint** uzlů a uzly podřízeného webu.|
|Zobrazit v prohlížeči|Zobrazí vybraný seznam ve webovém prohlížeči. Tento příkaz je k dispozici na některé seznamy v části **uvádí** uzel, který je součástí **seznamy a knihovny**.|

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Postupy: Přidání nebo odebrání připojení služby SharePoint](../sharepoint/how-to-add-or-remove-sharepoint-connections.md)|Popisuje kroky, které jsou požadovány pro přidání nového webu služby SharePoint **připojení služby SharePoint** uzel v **Průzkumníka serveru**.|

## <a name="see-also"></a>Viz také:
- [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)
