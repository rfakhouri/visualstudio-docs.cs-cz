---
title: Registrace sestavení zprostředkovatele komunikace obslužné rutiny příkazů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- interop assemblies, command handlers
- command handling with interop assemblies, registering
ms.assetid: 303cd399-e29d-4ea1-8abe-5e0b59c12a0c
caps.latest.revision: 20
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9d2822e9eef36806f5c251813925fb4244242519
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65705817"
---
# <a name="registering-interop-assembly-command-handlers"></a>Registrace obslužných rutin příkazů definičních sestavení
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Musíte zaregistrovat VSPackage [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] tak, aby integrované vývojové prostředí (IDE) směruje příkazy správně.  
  
 Ruční úpravou nebo pomocí souboru registrátora (.rgs) je možné aktualizovat registr. Další informace najdete v tématu [vytváření skriptů registrátoru](https://msdn.microsoft.com/library/cbd5024b-8061-4a71-be65-7fee90374a35).  
  
 Tuto funkci pomocí Managed Package Framework (MPF) poskytuje <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> třídy.  
  
 [Příkaz referenční příručka pro formátování tabulky](https://msdn.microsoft.com/09e9c6ef-9863-48de-9483-d45b7b7c798f) prostředky jsou umístěny v nespravované satelitní knihovny DLL uživatelského rozhraní.  
  
## <a name="command-handler-registration-of-a-vspackage"></a>Registrace obslužná rutina příkazu VSPackage  
 VSPackage funguje jako obslužné rutiny pro uživatelské rozhraní (UI) – na základě příkazů vyžaduje položku registru s názvem po sady VSPackage `GUID`. Tato položka registru určuje umístění souboru prostředků sady VSPackage uživatelského rozhraní a nabídky prostředků v rámci tohoto souboru. Samotné položky registru je umístěna ve složce HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\\*\<verze >* \Menus, kde  *\<verze >* je verze [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], například 9.0.  
  
> [!NOTE]
> Kořenová cesta HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<verze >* lze přepsat pomocí alternativního root, kdy [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] prostředí je inicializován. Další informace o kořenovou cestu, naleznete v tématu [instalace rozšíření VSPackages s Windows Installer](../../extensibility/internals/installing-vspackages-with-windows-installer.md).  
  
### <a name="the-ctmenu-resource-registry-entry"></a>Položky registru CTMENU prostředků  
 Struktura položky registru je:  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\<Version>\  
  Menus\  
    <GUID> = <Resource Information>  
```  
  
 \<*Identifikátor GUID*> je `GUID` sady VSPackage ve formuláři {XXXXXX-XXXX-XXXX-XXXX-XXXXXXXXX}.  
  
 *\<Informace o prostředku >* se skládá ze tří prvků oddělených čárkami. Tyto prvky jsou v pořadí:  
  
 \<*Cesta k knihovna DLL prostředků*>, \< *ID prostředku nabídky*>, \< *nabídka verze*>  
  
 Následující tabulka popisuje pole \< *informace o prostředku*>.  
  
|Prvek|Popis|  
|-------------|-----------------|  
|\<*Cesta k prostředku knihovny DLL*>|Toto je úplná cesta k prostředku knihovny DLL, která obsahuje prostředek nabídky nebo toto pole je ponecháno prázdné, že sady VSPackage prostředků knihovny DLL pro použití (jak je uvedeno v podklíči balíčky, ve kterém je zaregistrován VSPackage samotné).<br /><br /> Je to obvyklé toto pole nechat prázdné.|  
|\<*ID prostředku nabídky*>|To je ID prostředku `CTMENU` prostředek, který obsahuje všechny prvky uživatelského rozhraní pro sady VSPackage jako zkompilovaná ze [.vsct](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md) souboru.|  
|\<*Nabídka verze*>|Toto je číslo používané jako verze pro `CTMENU` prostředků. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] používá tuto hodnotu k určení, jestli je potřeba remerge obsah `CTMENU` prostředek s uloženou v mezipaměti všech `CTMENU` prostředky. Spuštěním příkazu devenv instalace se aktivuje remerge.<br /><br /> By měla tuto hodnotu původně nastavena na hodnotu 1 a zvýší po každé změně v `CTMENU` prostředků a před provedením remerge.|  
  
### <a name="example"></a>Příklad  
 Tady je příklad z několika záznamů prostředků:  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\9.0Exp\  
  Menus\  
    {019971D6-4685-11D2-B48A-0000F87572EB} = ,1, 10  
    {1b027a40-8f43-11d0-8d11-00a0c91bc942} = , 10211, 3  
```  
  
## <a name="see-also"></a>Viz také  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Příkazy a nabídky, které používají spolupracující sestavení](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)
