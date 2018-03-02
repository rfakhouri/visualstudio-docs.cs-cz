---
title: "Požadavky na vývoj řešení služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, prerequisites
- SharePoint development in Visual Studio, requirements
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 4591bef62d9e3d639e6dfca44c0b2625a8e02de5
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
---
# <a name="requirements-for-developing-sharepoint-solutions"></a>Požadavky na vývoj řešení služby SharePoint
 
Před použitím nástroje vývoj řešení služby SharePoint zahrnuté v sadě Visual Studio, musíte nainstalovat následující požadavky na systém:

- Visual Studio C# nebo Visual Basic nebo edici nástroje Visual Studio Application Lifecycle Management (ALM).

- [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] nainstalovat na 64-bit [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] nebo 64bitovou [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] R2.

     or

- [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] nainstalovat na 64-bit [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] nebo 64bitovou [!INCLUDE[winsvr08](../sharepoint/includes/winsvr08-md.md)] R2.

> [!NOTE]
> Když pouze serverové operační systémy jsou oficiálně podporované službou SharePoint, jsou povolené dvě klientské operační systémy: [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] a [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] SP1. Další informace najdete v tématu [Průvodce instalací služby SharePoint Server 2010 vývojáře pracovní stanice](http://go.microsoft.com/fwlink/?LinkID=164557).

Typy projektů obchodní Model dat připojení (BDC) vyžadují, aby [!INCLUDE[moss_14_long](../sharepoint/includes/moss-14-long-md.md)] se v systému nainstalována.

Pro vývoj řešení služby SharePoint v sadě Visual Studio, je nutné nainstalovat služby SharePoint na stejném počítači jako Visual Studio. Navíc SharePoint developer tools podporují pouze v samostatné konfiguraci SharePoint; (vzdálený) konfigurace farmy nepodporují.

> [!NOTE]
> Projekty SharePoint v sadě Visual Studio podporují pouze [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)]. Pokud vyberete [!INCLUDE[net_v40_long](../sharepoint/includes/net-v40-long-md.md)] nového projektu služby SharePoint, bude stále cíle [!INCLUDE[net_v35_long](../sharepoint/includes/net-v35-long-md.md)].

Další informace o tom, jak nainstalovat [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], najdete v části [instalaci sady Visual Studio](../install/install-visual-studio.md).

## <a name="vista-and-windows-7-user-account-control-uac"></a>Řízení uživatelských účtů v systémech Vista a Windows 7

[!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] a [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] začlenit funkce zabezpečení, která se označuje jako řízení uživatelských účtů (UAC). Pro vývoj řešení služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] na [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] a [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] systémy, nástroje Řízení uživatelských účtů vyžaduje, že spustíte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] jako správce systému. Na ploše otevřete místní nabídku pro [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]a potom zvolte **spustit jako správce**.

Ke konfiguraci zástupce na ploše vždy spustit jako správce, otevřete jeho místní nabídky, zvolte **vlastnosti**, vyberte **Upřesnit** tlačítko a pak vyberte **spustit jako správce**  zaškrtávací políčko.

Další informace najdete v tématu [pochopení a konfigurace řízení uživatelských účtů v systému Windows Vista](http://go.microsoft.com/fwlink/?LinkID=156476). a [řízení uživatelských účtů systému Windows 7](http://go.microsoft.com/fwlink/?LinkId=177523).

## <a name="sharepoint-permissions-considerations"></a>Důležité informace o oprávnění služby SharePoint

Pro vývoj řešení služby SharePoint, musíte mít dostatečná oprávnění ke spouštění a ladění řešení služby SharePoint. Chcete-li otestovat řešení služby SharePoint, ujistěte se, zda máte potřebná oprávnění pomocí následujících kroků:

1. Váš uživatelský účet přidáte jako správce systému.

2. Přidáte uživatelský účet jako správce farmy pro SharePoint server.

    1. V Centrální správě SharePoint, vyberte **spravovat skupiny správců farmy** odkaz.

    2. Na **správci farmy** vyberte **nový** tlačítko.

3. Přidat uživatelský účet ke skupině WSS_ADMIN_WPG.

## <a name="see-also"></a>Viz také

[Začínáme &#40; Vývoj pro SharePoint v sadě Visual Studio &#41;](../sharepoint/getting-started-sharepoint-development-in-visual-studio.md)