---
title: Dotazování. Soubor PDB | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PDB files
- .pdb files, querying
ms.assetid: 8da07d1c-2712-45f9-8fbf-f34040408a8a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dcc97fc6c508a47088cb2e96c9132c88c8fcb75c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54996805"
---
# <a name="querying-the-pdb-file"></a>Dotazování na soubor .Pdb
Soubor databáze programu (příponou PDB) je binární soubor, který obsahuje typ a symbolické ladicí informace shromážděné v průběhu kompilace a propojování projektu. Soubor PDB je vytvořen při kompilaci programu jazyka C/C++ pomocí **/zi** nebo **/zi** nebo [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], nebo [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] programovat s **/debug** možnost. Objektové soubory obsahují odkazy do souboru PDB pro informace o ladění. Další informace o souborech pdb, naleznete v tématu [soubory PDB](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yd4f8bd1(v=vs.100)). DIA aplikace můžete použít následující obecné kroky k získání podrobností o různých symboly, objektů a dat elementů v rámci spustitelnou bitovou kopii.  
  
### <a name="to-query-the-pdb-file"></a>K dotazování na soubor .pdb  
  
1.  Získání zdroje dat tak, že vytvoříte [idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md) rozhraní.  
  
    ```C++  
    CComPtr<IDiaDataSource> pSource;  
    hr = CoCreateInstance( CLSID_DiaSource,  
                           NULL,  
                           CLSCTX_INPROC_SERVER,  
                           __uuidof( IDiaDataSource ),  
                          (void **) &pSource);  
  
    if (FAILED(hr))  
    {  
        Fatal("Could not CoCreate CLSID_DiaSource. Register msdia80.dll." );  
    }  
    ```  
  
2.  Volání [idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) nebo [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) načíst informace o ladění.  
  
    ```C++  
    wchar_t wszFilename[ _MAX_PATH ];  
    mbstowcs( wszFilename, szFilename, sizeof( wszFilename )/sizeof( wszFilename[0] ) );  
    if ( FAILED( pSource->loadDataFromPdb( wszFilename ) ) )  
    {  
        if ( FAILED( pSource->loadDataForExe( wszFilename, NULL, NULL ) ) )  
        {  
            Fatal( "loadDataFromPdb/Exe" );  
        }  
    }  
    ```  
  
3.  Volání [idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md) otevřete [idiasession –](../../debugger/debug-interface-access/idiasession.md) se a získat informace o ladění.  
  
    ```C++  
    CComPtr<IDiaSession> psession;  
    if ( FAILED( pSource->openSession( &psession ) ) )   
    {  
        Fatal( "openSession" );  
    }  
    ```  
  
4.  Použijte metody v `IDiaSession` dotazu pro symboly ve zdroji dat.  
  
    ```C++  
    CComPtr<IDiaSymbol> pglobal;  
    if ( FAILED( psession->get_globalScope( &pglobal) ) )  
    {  
        Fatal( "get_globalScope" );  
    }  
    ```  
  
5.  Použití `IDiaEnum*` rozhraní možné vytvořit výčet a procházet symboly nebo další prvky ladicí informace.  
  
    ```C++  
    CComPtr<IDiaEnumTables> pTables;  
    if ( FAILED( psession->getEnumTables( &pTables ) ) )  
    {  
        Fatal( "getEnumTables" );  
    }  
    CComPtr< IDiaTable > pTable;  
    while ( SUCCEEDED( hr = pTables->Next( 1, &pTable, &celt ) ) && celt == 1 )  
    {  
         // Do something with each IDiaTable.  
    }  
    ```  
  
## <a name="see-also"></a>Viz také  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)