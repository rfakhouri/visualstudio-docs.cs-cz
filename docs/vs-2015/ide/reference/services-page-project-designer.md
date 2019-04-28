---
title: Stránka služby, Návrhář projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesServices
helpviewer_keywords:
- Services page in Project Designer
- Project Designer, Services page
ms.assetid: 6dd9e0fa-acba-4d7d-b081-705b0fc86ff5
caps.latest.revision: 30
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ed2e8ad333121a489c450a35daf81a368cd4aba8
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444721"
---
# <a name="services-page-project-designer"></a>Stránka Služby, návrhář projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Klientské aplikační služby nabízejí zjednodušený přístup ke [!INCLUDE[ajax_current_short](../../includes/ajax-current-short-md.md)] přihlášení, role a služby profilu v aplikacích Windows Forms a Windows Presentation Foundation (WPF). Můžete použít **služby** stránku **Návrháře projektu** povolení a konfigurace klientských aplikačních služeb pro váš projekt.  
  
 U klientských aplikačních služeb můžete použít centralizované serverové k ověřování uživatelů, určete každý uživatel přiřazenou roli nebo role a ukládání nastavení aplikace pro jednotlivé uživatele, které můžete sdílet přes síť. Další informace najdete v tématu [klientských aplikačních služeb](http://msdn.microsoft.com/library/1487d8df-089e-4f21-abfb-a791a652b58e).  
  
 Pro přístup **služby** stránky, vyberte uzel projektu v **Průzkumníku řešení**a potom klikněte na **vlastnosti** na **projektu** nabídky. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **služby** kartu.  
  
> [!NOTE]
> Klientské aplikační služby vyžadují plnou verzi rozhraní .NET Framework a nejsou podporovány v rozhraní .NET Framework Client Profile. Pokud **povolit klientské aplikační služby** zaškrtávací políčko je zakázaná. Ověřte, zda **Cílová architektura** je nastavená na rozhraní .NET Framework 3.5 nebo novější. Chcete-li zobrazit **Cílová architektura** nastavení v jazyce C#, otevřete Návrhář projektu a pak klikněte na tlačítko **aplikace** stránky. Chcete-li zobrazit **Cílová architektura** nastavení v jazyce Visual Basic, otevřete Návrhář projektu, klikněte na tlačítko **kompilaci** stránce a potom klikněte na **Upřesnit možnosti kompilace**.  
  
## <a name="task-list"></a>Seznam úkolů  
 [Postupy: Konfigurace klientských aplikačních služeb](http://msdn.microsoft.com/library/34a8688a-a32c-40d3-94be-c8e610c6a4e8)  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Konfigurace**  
 Tento ovládací prvek není na této stránce upravovat. Popis tohoto ovládacího prvku, naleznete v tématu [stránka kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) nebo [stránku sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Platforma**  
 Tento ovládací prvek není na této stránce upravovat. Popis tohoto ovládacího prvku, naleznete v tématu [stránka kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) nebo [stránku sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Povolit klientské aplikační služby**  
 Vyberte povolit klientské aplikační služby. Je nutné zadat umístění služby na **služby** stránku klientské aplikační služby.  
  
 **Používat ověřování Windows**  
 Označuje, že zprostředkovatel ověřování bude používat ověřování založené na Windows, to znamená, identity, které jsou součástí operačního systému Windows.  
  
 **Ověřování pomocí formulářů**  
 Označuje, že zprostředkovatel ověřování bude používat ověřování pomocí formulářů. To znamená, že vaše aplikace musí poskytovat uživatelského rozhraní pro přihlášení. Další informace najdete v tématu [jak: Implementace přihlášení uživatele u klientských aplikačních služeb](http://msdn.microsoft.com/library/5431a671-eb02-4e18-a651-24764fccec9a).  
  
 **Umístění služby ověřování**  
 Použít pouze s ověřování pomocí formulářů. Určuje umístění ověřovací služby.  
  
 **Volitelné: Poskytovatel přihlašovacích údajů**  
 Použít pouze s ověřování pomocí formulářů. Označuje <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> implementace, která se má zobrazit dialogové okno přihlášení, když vaše aplikace volá bude používat službu ověřování `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> metoda a předá prázdné řetězce nebo `null` parametrů. Když toto pole ponecháte prázdné, je nutné předat platné uživatelské jméno a heslo <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> metody. Jako název typu kvalifikovaného pro sestavení, je nutné zadat poskytovatele přihlašovacích údajů. Další informace najdete v tématu <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName> a [názvy sestavení](http://msdn.microsoft.com/library/8f8c2c90-f15d-400e-87e7-a757e4f04d0e). Ve své nejjednodušší podobě vypadá podobně jako v následujícím příkladu představuje název typu kvalifikovaného pro sestavení: `MyNamespace.MyLoginClass, MyAssembly`  
  
 **Umístění služby role**  
 Určuje umístění služby rolí.  
  
 **Nastavení webové služby umístění**  
 Určuje umístění služby profilu (nastavení webu).  
  
 **Pokročilé**  
 Otevře [rozšířená nastavení pro dialogové okno služby](../../ide/reference/advanced-settings-for-services-dialog-box.md), což vám umožní potlačit výchozí chování. Například můžete použít toto dialogové okno zadat databázi pro offline úložiště namísto použití místního systému souborů. Další informace najdete v tématu [rozšířená nastavení pro dialogové okno služby](../../ide/reference/advanced-settings-for-services-dialog-box.md).  
  
## <a name="see-also"></a>Viz také  
 [Klientské aplikační služby](http://msdn.microsoft.com/library/1487d8df-089e-4f21-abfb-a791a652b58e)   
 [Upřesňující nastavení pro dialogové okno služby](../../ide/reference/advanced-settings-for-services-dialog-box.md)   
 [Postupy: Konfigurace klientských aplikačních služeb](http://msdn.microsoft.com/library/34a8688a-a32c-40d3-94be-c8e610c6a4e8)   
 [Stránka kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md)   
 [Úvod do Návrháře projektu](http://msdn.microsoft.com/898dd854-c98d-430c-ba1b-a913ce3c73d7)
