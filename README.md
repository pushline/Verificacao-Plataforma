## Include VerificacaoPlataforma SA:MP

Este é um include que tem a função de verificar se o jogador está usando um `mobile` ou um `computador`. Leia as categorias abaixo para se manter informado.

English > [README](https://github.com/ocalasans/Verificacao-Plataforma/blob/main/README.eng.md).

-----------------------

### Como instalar?

Você deve fazer o download do include. Depois de tê-lo feito, você deverá colocar o include na pasta (pawno > include). Após ter feito isso, abra o arquivo pwn do seu Gamemode e coloque o seguinte código abaixo dos seus outros includes:
```pawn
#include <VerificacaoPlataforma>
```

-----------------------

### Include necessária

* [Pawn.RakNet](https://github.com/katursis/Pawn.RakNet).

> [!WARNING]
> Se o usuário não tiver ativado a biblioteca [Pawn.RakNet](https://github.com/katursis/Pawn.RakNet), receberá um erro de número `111`.

-----------------------

### Como funciona?

Assim que o jogador se conecta ao servidor, o include automaticamente verifica em qual plataforma ele está, seja `mobile` ou `computador`, com a assistência do [Pawn.RakNet](https://github.com/katursis/Pawn.RakNet). Para conferir a plataforma do jogador, basta utilizar a função booleana `IsPlayerAndroid`. Abaixo, estão alguns exemplos:

Com o `if`
```pawn
CMD:plataforma(playerid)
{
    if(IsPlayerAndroid(playerid))
        SendClientMessage(playerid, 0xFFFFFFFF, "Voce esta conectado pela plataforma Mobile.");
    //
    else if(!IsPlayerAndroid(playerid)) // Pode ser somente else.
        SendClientMessage(playerid, 0xFFFFFFFF, "Voce esta conectado pela plataforma Computador.");
    //
    return true;
}
```

Sem o `if`
```pawn
CMD:plataforma(playerid)
{
    new string[128];
    //
    format(string, sizeof(string), "Voce esta conectado pela plataforma %s.", IsPlayerAndroid(playerid) ? ("Mobile") : ("Computador"));
    SendClientMessage(playerid, 0xFFFFFFFF, string);
    //
    return true;
}
```

-----------------------

Este include também possui uma função chamada `PlayerHasAutoAim`. Essa função consiste em verificar se o jogador está com mira automática ou se está sem a mira automática, conhecida como `LockOn`. Abaixo, estão alguns exemplos:

Com o `if`
```pawn
CMD:mira(playerid)
{
    if(PlayerHasAutoAim(playerid))
        SendClientMessage(playerid, 0xFFFFFFFF, "Sua mira automatica esta Ativada.");
    //
    else if(!PlayerHasAutoAim(playerid)) // Pode ser somente else.
        SendClientMessage(playerid, 0xFFFFFFFF, "Sua mira automatica esta Desativada.");
    //
    return true;
}
```

Sem o `if`
```pawn
CMD:mira(playerid)
{
    new string[128];
    //
    format(string, sizeof(string), "Sua mira automatica esta %s.", PlayerHasAutoAim(playerid) ? ("Ativada") : ("Desativada"));
    SendClientMessage(playerid, 0xFFFFFFFF, string);
    //
    return true;
}
```

-----------------------

### Informações de contato

Instagram: [ocalasans](https://instagram.com/ocalasans)   
YouTube: [Calasans](https://www.youtube.com/@ocalasans)   
Discord: ocalasans   
Comunidade: [SA:MP Programming Community©](https://abre.ai/samp-spc)
