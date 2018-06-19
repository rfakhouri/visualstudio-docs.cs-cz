---
title: 'Návod: Vytvoření vlastního instalátoru pro aplikaci ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, custom installer
- installer [ClickOnce], custom
- deploying applications [ClickOnce], custom installer
- InPlaceHostingManager [ClickOnce], custom installer
- custom installer [ClickOnce]
ms.assetid: fb222cc5-8aeb-4b94-8c49-b93e342f5f69
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cdef0199aa55d6981761a20804f9f209a1a0fdc4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31565416"
---
# <a name="walkthrough-creating-a-custom-installer-for-a-clickonce-application"></a>Návod: Vytvoření vlastního instalátoru pro aplikaci ClickOnce
Každá aplikace ClickOnce na základě souboru .exe můžete bezobslužně nainstalovat a aktualizovat vlastní instalační program. Vlastní instalační program můžete implementovat vlastní uživatelské rozhraní během instalace, včetně vlastních dialogových oken pro operace zabezpečení a údržby. K provedení operace instalace, používá vlastní instalační program <xref:System.Deployment.Application.InPlaceHostingManager> třídy. Tento návod ukazuje, jak vytvořit vlastní instalační program, který nainstaluje aplikaci ClickOnce bezobslužně.  
  
## <a name="prerequisites"></a>Požadavky  
  
### <a name="to-create-a-custom-clickonce-application-installer"></a>Chcete-li vytvořit vlastní instalační program aplikace ClickOnce  
  
1.  V aplikaci ClickOnce přidejte odkazy na System.Deployment a System.Windows.Forms.  
  
2.  Přidejte novou třídu do vaší aplikace a zadat libovolný název. Tento návod používá název `MyInstaller`.  
  
3.  Přidejte následující `Imports` nebo `using` příkazů do horní části nové třídy.  
  
    ```vb  
    Imports System.Deployment.Application  
    Imports System.Windows.Forms  
    ```  
  
    ```csharp  
    using System.Deployment.Application;  
    using System.Windows.Forms;  
    ```  
  
4.  Přidejte následující metody na třídu.  
  
     Tyto metody volání <xref:System.Deployment.Application.InPlaceHostingManager> metody stažení manifest nasazení vyhodnocení příslušných oprávnění, požádá uživatele o oprávnění k instalaci a pak stáhnout a nainstalovat aplikaci do mezipaměti ClickOnce. Vlastní instalační program můžete určit, zda je předem důvěryhodné aplikace ClickOnce, nebo můžete odložit rozhodnutí vztah důvěryhodnosti k <xref:System.Deployment.Application.InPlaceHostingManager.AssertApplicationRequirements%2A> volání metody. Tento kód předem důvěřuje aplikace.  
  
    > [!NOTE]
    >  Oprávnění přiřazená podle předem důvěřující nesmí překročit oprávnění kód vlastní instalační program.  
  
     [!code-vb[System.Deployment.Application.InPlaceHostingManager#1](../deployment/codesnippet/VisualBasic/walkthrough-creating-a-custom-installer-for-a-clickonce-application_1.vb)]
     [!code-csharp[System.Deployment.Application.InPlaceHostingManager#1](../deployment/codesnippet/CSharp/walkthrough-creating-a-custom-installer-for-a-clickonce-application_1.cs)]  
  
5.  Chcete-li se pokusit o instalaci z vašeho kódu, zavolejte `InstallApplication` metoda. Například, pokud jste s názvem vaší třídy `MyInstaller`, může zavolat `InstallApplication` následujícím způsobem.  
  
    ```vb  
    Dim installer As New MyInstaller()  
    installer.InstallApplication("\\myServer\myShare\myApp.application")  
    MessageBox.Show("Installer object created.")  
    ```  
  
    ```csharp  
    MyInstaller installer = new MyInstaller();  
    installer.InstallApplication(@"\\myServer\myShare\myApp.application");  
    MessageBox.Show("Installer object created.");  
    ```  
  
## <a name="next-steps"></a>Další kroky  
 Aplikace ClickOnce můžete také přidat vlastní logiky aktualizace, včetně vlastní uživatelské rozhraní zobrazit během procesu aktualizace. Další informace naleznete v tématu <xref:System.Deployment.Application.UpdateCheckInfo>. Aplikace ClickOnce může také potlačit standardní položku nabídky Start, zástupce a položky Přidat nebo odebrat programy pomocí `<customUX>` elementu. Další informace najdete v tématu [ \<entryPoint > Element](../deployment/entrypoint-element-clickonce-application.md) a <xref:System.Deployment.Application.DownloadApplicationCompletedEventArgs.ShortcutAppId%2A>.  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – Manifest aplikace](../deployment/clickonce-application-manifest.md)   
 [\<entryPoint > elementu](../deployment/entrypoint-element-clickonce-application.md)