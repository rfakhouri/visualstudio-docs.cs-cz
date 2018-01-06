---
title: "Zabezpečení pro řešení služby SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- security [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, security
ms.assetid: 5ab33141-ba82-4960-8b29-3c907127fea6
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 22ef16c40fb2d70ae7e1b835860b74843abe57d3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="security-for-sharepoint-solutions"></a>Zabezpečení pro řešení služby SharePoint
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]zahrnuje následující funkce pro zlepšení zabezpečení aplikací služby SharePoint.  
  
## <a name="safe-control-entries"></a>Bezpečné ovládací prvek položky  
 Každá položka projektu služby SharePoint vytvořené v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] má **bezpečné položky řízení** vlastnost, která představuje sejfu ovládací prvky kolekce. Jeho **bezpečné** dílčí vlastnosti umožňuje určit ovládacích prvků, které považujete za bezpečné. Další informace najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) a [zadání bezpečné webové části](http://go.microsoft.com/fwlink/?LinkId=177521).  
  
## <a name="allowpartiallytrustedcallers-attribute"></a>Atribut AllowPartiallyTrustedCallers  
 Ve výchozím nastavení můžete přístup pouze aplikace, které jsou plně důvěryhodný systémem zabezpečení (CA) přístup kódu modulu runtime sestavení sdílené spravovaného kódu. Označení plně důvěryhodný pro sestavení pomocí atributu AllowPartiallyTrustedCallers umožňuje částečně důvěryhodné sestavení pro přístup k ní.  
  
 Přidání atributu AllowPartiallyTrustedCallers u jakéhokoliv řešení služby SharePoint, která není nasazena na systému globální mezipaměti sestavení ([!INCLUDE[TLA2#tla_gac](../sharepoint/includes/tla2sharptla-gac-md.md)]). To zahrnuje řešení v izolovaném prostoru nebo řešení, které jsou nasazeny do adresáře Bin aplikace služby SharePoint. Další informace najdete v tématu [změny zabezpečení verze 1 pro rozhraní Microsoft .NET Framework](http://go.microsoft.com/fwlink/?LinkId=177515) a [nasazení webové části v SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkId=177509).  
  
## <a name="safe-against-script-property"></a>Bezpečné proti vlastnosti skriptu  
 *Skript vkládání* je vkládání potenciálně škodlivého kódu do ovládacích prvků nebo webové stránky. K ochraně weby SharePoint 2010 pro vložení skriptu, přispěvatelé nemůžete zobrazit nebo upravit webové části nebo jejich vlastnosti ve výchozím nastavení. Toto chování je řízena SafeControl – atribut nazvaný SafeAgainstScript. V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], nastavte tento atribut v položce projektu **bezpečné položky řízení** dílčí vlastnosti **skriptu bezpečné proti**. Další informace najdete v tématu [poskytování balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md) a [postup: ovládací prvky označit jako bezpečné ovládací prvky](../sharepoint/how-to-mark-controls-as-safe-controls.md).  
  
## <a name="vista-and-windows-7-user-account-control"></a>Vista a Windows 7 nástroje Řízení uživatelských účtů  
 [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)]a [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] začlenit funkce zabezpečení známé jako řízení uživatelských účtů (UAC). Pro vývoj řešení služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] na [!INCLUDE[windowsver](../sharepoint/includes/windowsver-md.md)] a [!INCLUDE[win7](../sharepoint/includes/win7-md.md)] systémy, nástroje Řízení uživatelských účtů vyžaduje, že spustíte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] jako správce systému. Z **spustit** nabídce otevřete místní nabídku pro [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]a potom zvolte **spustit jako správce**.  
  
 Ke konfiguraci [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zástupce vždy spustit jako správce, otevřete jeho místní nabídky, zvolte **vlastnosti**, vyberte **Upřesnit** v tlačítko **vlastnosti**dialogové okno a potom vyberte **spustit jako správce** zaškrtávací políčko.  
  
 Další informace najdete v tématu [pochopení a konfigurace řízení uživatelských účtů v systému Windows Vista](http://go.microsoft.com/fwlink/?LinkID=156476). a [řízení uživatelských účtů systému Windows 7](http://go.microsoft.com/fwlink/?LinkId=177523).  
  
## <a name="sharepoint-permissions-considerations"></a>Důležité informace o oprávnění služby SharePoint  
 Pro vývoj řešení služby SharePoint, musíte mít dostatečná oprávnění ke spouštění a ladění řešení služby SharePoint. Chcete-li otestovat řešení služby SharePoint, ujistěte se, zda máte potřebná oprávnění pomocí následujících kroků:  
  
1.  Váš uživatelský účet přidáte jako správce systému.  
  
2.  Přidáte uživatelský účet jako správce farmy pro SharePoint server.  
  
    1.  V Centrální správa SharePoint 2010, vyberte **spravovat skupiny správců farmy** odkaz.  
  
    2.  Na **správci farmy** vyberte **nový** nabídky  
  
3.  Přidat uživatelský účet ke skupině WSS_ADMIN_WPG.  
  
## <a name="additional-security-resources"></a>Další bezpečnostní prostředky  
 Další informace o problémy se zabezpečením naleznete v následujících tématech.  
  
### <a name="visual-studio-security"></a>Zabezpečení v sadě Visual Studio  
  
-   [Zabezpečení a oprávnění uživatele](http://go.microsoft.com/fwlink/?LinkId=177503)  
  
-   [Zabezpečení v rozhraní .NET Framework kód a nativní](http://go.microsoft.com/fwlink/?LinkId=177504)  
  
-   [Zabezpečení v rozhraní .NET Framework](http://go.microsoft.com/fwlink/?LinkId=177502)  
  
### <a name="sharepoint-security"></a>Zabezpečení služby SharePoint  
  
-   [SharePoint Foundation správy a zabezpečení](http://go.microsoft.com/fwlink/?LinkId=177501)  
  
-   [SharePoint Security Resource Center](http://go.microsoft.com/fwlink/?LinkId=177498)  
  
-   [Zabezpečení webových částí služby SharePoint Foundation](http://go.microsoft.com/fwlink/?LinkId=177511)  
  
-   [Vylepšení zabezpečení webových aplikací: Hrozby a opatření](http://go.microsoft.com/fwlink/?LinkID=140080)  
  
### <a name="general-security"></a>Obecné zabezpečení  
  
-   [MSDN Security Development Lifecycle](http://go.microsoft.com/fwlink/?LinkID=147149)  
  
-   [Vytváření aplikací ASP.NET zabezpečení: Ověřování, autorizace a zabezpečenou komunikaci](http://go.microsoft.com/fwlink/?LinkId=177494)  
  
## <a name="see-also"></a>Viz také  
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md)  
  
  