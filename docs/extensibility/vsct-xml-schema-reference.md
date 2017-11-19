---
title: "Referenční dokumentace schématu VSCT XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio command table configuration files (VSCT), XML schema
- VSCT XML schema elements
ms.assetid: 49e7efae-e713-4762-a824-96fdaf92cdc9
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1fc82041f8ab2790c63c271f85d573a3105ab8b0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="vsct-xml-schema-reference"></a>Referenční dokumentace schématu VSCT XML
Poskytne tabulku prvky kompilátoru tabulky příkaz schématu, povolené podřízených elementů a atributů pro každý.  
  
 Soubor konfigurace (.vsct) tabulky na základě XML příkaz definuje příkaz prvky, které poskytuje VSPackage integrované vývojové prostředí (IDE). Tyto prvky patří položky nabídky, nabídek, panely nástrojů a pole se seznamem.  
  
> [!NOTE]
>  Kompilátor VSCT můžete spustit preprocesor na soubor .vsct. Protože to je obvykle zahrnuje C++ preprocesoru, že můžete definovat a makra, které mají stejnou syntaxí, který se používá v souborech C++. Příklady to jsou součástí .vsct souboru, který **nový projekt** Průvodce vytvoří pro projekt VSPackage.  
  
## <a name="optional-elements"></a>Volitelné elementy  
 Některé VSCT prvky jsou volitelné. Pokud `Parent` argument není zadán, bude možné implicitní Group_Undefined:0. Pokud `Icon` argument není zadán, bude možné implicitní guidOfficeIcon:msotcidNoIcon. Pokud je definován klávesovou zkratku, emulace, který se obvykle nepoužívá, je volitelný.  
  
 Rastrový obrázek položky může být vložen v době kompilace zadáním umístění pruhu rastrového obrázku v `href` argument. Rastrový obrázek pruhu je během sloučení zkopírovány spíše než extrahovat z této knihovny DLL prostředků. Když `href` argumentu k dispozici, `usedList` argument používá jen volitelně, a všechny sloty na pruhu rastrového obrázku jsou považovány za použít.  
  
 Všechny hodnoty GUID a ID musí být definovány pomocí symbolické názvy. Názvy těchto může být definována v hlavičkových souborů nebo v VSCT \<symboly > oddíly. Symbolické názvy musí být místní, vloženými prostřednictvím \<zahrnout > elementy, nebo odkazuje \<Extern > elementy. Symbolický název je naimportována ze zadané v záhlaví souboru \<Extern > elementu je-li postupuje jednoduchý vzor #define hodnotu SYMBOL. Hodnota může být další symbol, tak dlouho, dokud tento symbol byl předtím definovaný. Identifikátor GUID definice musí mít formát buď OLE nebo C++. ID hodnoty mohou být desetinných míst nebo šestnáctkových číslic, které jsou 0 x, jak je znázorněno v následující řádky:  
  
-   {6D484634-E53D-4a2c-ADCB-55145C9362C8}  
  
-   {0x6d484634, 0xe53d, 0x4a2c, {0xad, 0xCB, 0x55, 0x14, 0x5c poslední, 0x93, 0x62, 0xc8}}  
  
 XML – komentáře mohou být použity, ale je může zahodit nástroje odezvy grafické uživatelské rozhraní (GUI). Obsah \<Poznámky > elementy zaručeně nakládat bez ohledu na formát.  
  
## <a name="schema-hierarchy"></a>Schéma hierarchie  
 Soubor .vsct obsahuje následující hlavní prvky.  
  
 [CommandTable Element](../extensibility/commandtable-element.md)  
  
 [Extern – Element](../extensibility/extern-element.md)  
  
 [Zahrňte prvek](../extensibility/include-element.md)  
  
 [Definování elementu](../extensibility/define-element.md)  
  
 [Element příkazy](../extensibility/commands-element.md)  
  
 [CommandPlacements Element](../extensibility/commandplacements-element.md)  
  
 [VisibilityConstraints Element](../extensibility/visibilityconstraints-element.md)  
  
 [Element klíčových vazeb](../extensibility/keybindings-element.md)  
  
 [UsedCommands Element](../extensibility/usedcommands-element.md)  
  
 [Nadřazený Element](../extensibility/parent-element.md)  
  
 [Icon – Element](../extensibility/icon-element.md)  
  
 [Element řetězce](../extensibility/strings-element.md)  
  
 [Element Command příznak](../extensibility/command-flag-element.md)  
  
 [Element symboly](../extensibility/symbols-element.md)  
  
 [Podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md)  
  
## <a name="see-also"></a>Viz také  
 [Jak přidat VSPackages prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Směrování příkazů v VSPackages](../extensibility/internals/command-routing-in-vspackages.md)