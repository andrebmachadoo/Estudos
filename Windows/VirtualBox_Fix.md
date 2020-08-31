# Corrigir o ***WHvSetupPartition failed*** no Virtual box

```
Falha ao abrir uma sessão para a máquina virtual Win10.

Call to WHvSetupPartition failed: ERROR_SUCCESS (Last=0xc000000d/87) (VERR_NEM_VM_CREATE_FAILED).

Código de Resultado: E_FAIL (0x80004005)
Componente: ConsoleWrap
Interface: IConsole {872da645-4a9b-1727-bee2-5585105b9eed}
```

1.  Vá em Ativar/Destivar recursos do windows e:
    - ***Desativar*** Hyper-V 
    - ***Ativar*** Virtual Machine Platform(Plataforma para Maquina Virtual)
    - ***Desativar*** Windows Sandbox(Area restrita do windows)
    - Confirme as alterações e ***não reinicie ainda***
2. Abra o Power Shell como Admin e execute o comando 
    ```sh
    bcdedit /set hypervisorlaunchtype off
    ```
3. Reinicie o PC.
    
