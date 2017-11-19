---
title: "Stránka služby, Návrhář projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.ProjectPropertiesServices
helpviewer_keywords:
- Services page in Project Designer
- Project Designer, Services page
ms.assetid: 6dd9e0fa-acba-4d7d-b081-705b0fc86ff5
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0800884a03544aec822d31cf64fd47a4f63f3e07
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="services-page-project-designer"></a>Stránka Služby, návrhář projektu
Klient aplikačních služeb poskytují zjednodušenou přístup k [!INCLUDE[ajax_current_short](../../ide/reference/includes/ajax_current_short_md.md)] přihlášení, rolí a profilu služby z aplikací Windows Forms a Windows Presentation Foundation (WPF). Můžete použít **služby** stránky **Návrhář projektu** povolit a nakonfigurovat klientské aplikační služby pro váš projekt.  
  
 U klientských aplikačních služeb slouží k ověřování uživatelů, určete, každý uživatel přiřazenou roli nebo role a ukládat uživatelská nastavení aplikace, které můžete sdílet přes síť centralizovaný server. Další informace najdete v tématu [klientské aplikační služby](/dotnet/framework/common-client-technologies/client-application-services).  
  
 Pro přístup k **služby** vyberte uzel projektu v **Průzkumníku řešení**a potom klikněte na **vlastnosti** na **projektu** nabídky. Když **Návrhář projektu** se zobrazí, klikněte na tlačítko **služby** kartě.  
  
> [!NOTE]
>  Klient aplikačních služeb vyžadují plnou verzi rozhraní .NET Framework a nejsou podporovány v profil klienta rozhraní .NET Framework. Pokud **povolit klientské aplikační služby** zaškrtávací políčko je zakázáno, ověřte, zda **cílové rozhraní** je nastaven na rozhraní .NET Framework 3.5 nebo novější. Chcete-li zobrazit **cílové rozhraní** nastavení v jazyce C#, otevřete v Návrháři projektu a klikněte **aplikace** stránky. Chcete-li zobrazit **cílové rozhraní** nastavení v jazyce Visual Basic, otevřete v Návrháři projektu, klikněte na **zkompilovat** a pak klikněte na tlačítko **Upřesnit možnosti kompilace**.  
  
## <a name="task-list"></a>Seznam úloh  
 [Postupy: Konfigurace klientských aplikačních služeb](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Konfigurace**  
 Tento ovládací prvek se nedá upravovat na této stránce. Popis tohoto ovládacího prvku naleznete v tématu [stránka kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) nebo [stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Platforma**  
 Tento ovládací prvek se nedá upravovat na této stránce. Popis tohoto ovládacího prvku naleznete v tématu [stránka kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md) nebo [stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md).  
  
 **Povolit klientské aplikační služby**  
 Vyberte, chcete-li povolit klientské aplikační služby. Je nutné zadat umístění služeb v **služby** stránky používat klientské aplikační služby.  
  
 **Ověřování systému Windows**  
 Označuje, že zprostředkovatel ověřování bude používat ověřování systému Windows, který je identity, které jsou součástí operačního systému Windows.  
  
 **Ověřování pomocí formulářů**  
 Označuje, že zprostředkovatel ověřování použije ověřování pomocí formulářů. To znamená, že vaše aplikace musí poskytovat uživatelské rozhraní pro přihlášení. Další informace najdete v tématu [postupy: implementace přihlášení uživatele u klientských aplikačních služeb](/dotnet/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services).  
  
 **Umístění služby ověřování**  
 Použít pouze s ověřování pomocí formulářů. Určuje umístění ověřovací služby.  
  
 **Volitelné: Přihlašovací údaje poskytovatele**  
 Použít pouze s ověřování pomocí formulářů. Určuje, <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider> implementace, který ověřovací služby bude používat pro zobrazit dialogové okno přihlášení, kdy aplikace volá `static` <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> metoda a předává prázdné řetězce nebo `null` pro parametry. Když toto pole ponecháte prázdné, je nutné předat platné uživatelské jméno a heslo k <xref:System.Web.Security.Membership.ValidateUser%2A?displayProperty=fullName> metoda. Jako název sestavení kvalifikovaný typ musíte zadat přihlašovací údaje poskytovatele. Další informace najdete v tématu <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=fullName> a [názvy sestavení](/dotnet/framework/app-domains/assembly-names). V nejjednodušší podobě název sestavení kvalifikovaný typ vypadá podobně jako v následujícím příkladu:`MyNamespace.MyLoginClass, MyAssembly`  
  
 **Umístění služby role**  
 Určuje umístění služby rolí.  
  
 **Nastavení webové služby umístění**  
 Určuje umístění služby profilu (nastavení webové).  
  
 **Upřesnit**  
 Otevře se [rozšířená nastavení pro dialogové okno služby](../../ide/reference/advanced-settings-for-services-dialog-box.md), který můžete přepsat výchozí chování. Například můžete toto dialogové okno zadat databázi pro offline úložiště místo použití místního systému souborů. Další informace najdete v tématu [rozšířená nastavení pro dialogové okno služby](../../ide/reference/advanced-settings-for-services-dialog-box.md).  
  
## <a name="see-also"></a>Viz také  
 [Klient aplikačních služeb](/dotnet/framework/common-client-technologies/client-application-services)   
 [Rozšířená nastavení pro dialogové okno služby](../../ide/reference/advanced-settings-for-services-dialog-box.md)   
 [Postupy: Konfigurace klientských aplikačních služeb](/dotnet/framework/common-client-technologies/how-to-configure-client-application-services)   
 [Stránka kompilovat, Návrhář projektu (Visual Basic)](../../ide/reference/compile-page-project-designer-visual-basic.md)   
 [Stránka sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md)   
