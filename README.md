# PS2 Saves para PCSX2

## Estrutura

```
saves/
├── Burnout3-USA.ps2          (BASLUS-21050)
├── NFS-MostWanted-USA.ps2    (BASLUS-21351)
└── [outros jogos]-USA.ps2
```

## Como adicionar novos saves

### 1. Baixar saves

- **GameFAQs**: https://gamefaqs.gamespot.com (busque pelo jogo → Saves)
- **PS2-HOME**: https://www.ps2-home.com/forum/viewtopic.php?t=14285

Formatos suportados: `.psu`, `.max`, `.psv`, `.cbs`, `.xps`, `.sps`

### 2. Instalar mymcplus (apenas uma vez)

```bash
cd /Users/velrino/Documents/ps2/saves
python3 -m venv venv
source venv/bin/activate
pip install mymcplus
```

### 3. Criar memory card e importar save

```bash
source venv/bin/activate
python -m mymcplus NomeDoJogo-USA.ps2 format
python -m mymcplus NomeDoJogo-USA.ps2 import /caminho/do/save.psu
python -m mymcplus NomeDoJogo-USA.ps2 dir  # verificar
```

### 4. No PCSX2

1. Settings → Memory Cards
2. Folder: `/Users/velrino/Documents/ps2/saves`
3. Selecionar o `.ps2` do jogo no Slot 1

## Regiões

⚠️ **O save deve ser da mesma região do jogo!**

| Código | Região |
|--------|--------|
| SLUS / BASLUS | USA (NTSC-U) |
| SLES / BESLES | Europa (PAL) |
| SLPM | Japão (NTSC-J) |

## Comandos úteis

```bash
# Listar saves no memory card
python -m mymcplus Jogo.ps2 dir

# Exportar save
python -m mymcplus Jogo.ps2 export BASLUS-XXXXX save.psu

# Deletar save
python -m mymcplus Jogo.ps2 delete BASLUS-XXXXX
```
