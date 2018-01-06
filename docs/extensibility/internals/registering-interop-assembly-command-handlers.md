---
title: "Registrace sestavení vzájemné spolupráce obslužné rutiny příkazů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop assemblies, command handlers
- command handling with interop assemblies, registering
ms.assetid: 303cd399-e29d-4ea1-8abe-5e0b59c12a0c
caps.latest.revision: "19"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a25f8adc91efe9d9e8b96079b4fe2e35145abf25
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="registering-interop-assembly-command-handlers"></a>Registrace sestavení vzájemné spolupráce obslužné rutiny příkazů
VSPackage musíte zaregistrovat u [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tak, aby integrované vývojové prostředí (IDE) směruje jeho příkazy správně.  
  
 Ruční úpravou nebo pomocí souboru registrátora (.rgs), můžete aktualizovat registr. Další informace najdete v tématu [vytváření skripty registrátora](/cpp/atl/creating-registrar-scripts).  
  
 Spravované balíček Framework (MPF) poskytuje tuto funkci prostřednictvím <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> třídy.  
  
 [Příkaz odkaz na tabulku formátu](http://msdn.microsoft.com/en-us/09e9c6ef-9863-48de-9483-d45b7b7c798f) prostředky jsou umístěny v nespravované satelitní knihovny DLL uživatelského rozhraní.  
  
## <a name="command-handler-registration-of-a-vspackage"></a>Příkaz obslužná rutina registrace VSPackage  
 VSPackage funguje jako obslužná rutina pro uživatelské rozhraní (UI) – na základě příkazy vyžaduje záznam registru s názvem, jako VSPackage `GUID`. Tato položka registru určuje umístění souboru prostředků VSPackage uživatelského rozhraní a nabídky prostředek v rámci tohoto souboru. Položky registru, samotné se nachází v HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\*\<verze >*\Menus, kde  *\<verze >* je verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], například 9.0.  
  
> [!NOTE]
>  Kořenové cestě HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<verze >* lze přepsat pomocí náhradní root, kdy [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí je inicializován. Další informace o kořenovou cestu najdete v tématu [instalaci VSPackages pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md).  
  
### <a name="the-ctmenu-resource-registry-entry"></a>Položky registru prostředků CTMENU  
 Struktura položky registru je:  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\<Version>\  
  Menus\  
    <GUID> = <Resource Information>  
```  
  
 \<*Identifikátor GUID*> je `GUID` z VSPackage ve formuláři {XXXXXX-XXXX-XXXX-XXXX-XXXXXXXXX}.  
  
 *\<Informace o prostředku >* se skládá z uvedených položek oddělených čárkami. Tyto prvky jsou v pořadí:  
  
 \<*Cesta prostředku DLL*>, \< *ID prostředku nabídky*>, \< *verze nabídky*>  
  
 Následující tabulka popisuje pole \< *informace o prostředku*>.  
  
|Prvek|Popis|  
|-------------|-----------------|  
|\<*Cesta k DLL prostředků*>|Toto je úplná cesta prostředku DLL, která obsahuje prostředek nabídky nebo to je ponecháno prázdné, označující, že VSPackage prostředků knihovny DLL je pro použití (jak je uvedeno v podklíči balíčky, kde je registrovaná VSPackage sám sebe).<br /><br /> Se obvykle to pole ponechat prázdné.|  
|\<*ID prostředku nabídky*>|Toto je ID prostředku `CTMENU` prostředek, který obsahuje všechny prvky uživatelského rozhraní pro VSPackage jako kompilují ze [.vsct](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md) souboru.|  
|\<*Nabídka verze*>|Toto je použité jako verze pro `CTMENU` prostředků. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]Tato hodnota používá k určení, jestli je třeba remerge obsah `CTMENU` prostředek s své mezipaměti všech `CTMENU` prostředky. Remerge se aktivuje při provádění příkazu devenv instalační program.<br /><br /> Tato hodnota by měl původně být nastavena na hodnotu 1 a zvýší po každé změně v `CTMENU` prostředků a před provedením remerge.|  
  
### <a name="example"></a>Příklad  
 Tady je příklad několik položek prostředků:  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\9.0Exp\  
  Menus\  
    {019971D6-4685-11D2-B48A-0000F87572EB} = ,1, 10  
    {1b027a40-8f43-11d0-8d11-00a0c91bc942} = , 10211, 3  
```  
  
## <a name="see-also"></a>Viz také  
 [Jak přidat VSPackages prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Příkazy a nabídky, které používají spolupracující sestavení](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)