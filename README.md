# unimatrix-cymag

Versión personalizada de [unimatrix](https://github.com/will8211/unimatrix) que muestra la lluvia Matrix en **dos colores: cian y magenta**, elegidos de forma **aleatoria por carácter**, usando **katakana y klingon (pIqaD)**.

## Características

- 🌈 Dos colores: cian (`COLOR_CYAN`) y magenta (`COLOR_MAGENTA`)
- 🎲 Cada carácter elige su color al azar
- ⚡ Velocidad por defecto: `95` (fluido, casi sin delay)
- 🈶 Caracteres por defecto: katakana japonés + klingon pIqaD

## Requisitos

- Python 3
- `ncurses` (incluido en la librería estándar de Python)
- Fuente con soporte de klingon pIqaD (`Code2000` o `Klingon-pIqaD`), instalable en Arch con:
  ```bash
  paru -S ttf-code2000
  ```

## Instalación

```bash
# Copiar los archivos a tu PATH
cp unimatrix-cymag.py ~/.local/bin/
cp unimatrix-cymag ~/.local/bin/
chmod +x ~/.local/bin/unimatrix-cymag ~/.local/bin/unimatrix-cymag.py
```

Opcional, alias en `.zshrc`:

```zsh
alias unimatrix='unimatrix-cymag'
```

## Uso

```bash
unimatrix-cymag        # cian + magenta, katakana + klingon, velocidad 95
unimatrix-cymag -b     # caracteres en negrita
unimatrix-cymag -s 85  # velocidad personalizada (0-100)
unimatrix-cymag -t 10  # salir a los 10 segundos
unimatrix-cymag -l kn  # solo katakana + números
```

## Opciones heredadas de unimatrix

| Opción | Descripción |
|---|---|
| `-a` | Scroll asíncrono |
| `-b` | Solo caracteres en negrita |
| `-n` | Sin negrita |
| `-s SPEED` | Velocidad (0-100, default 95) |
| `-t TIME` | Salir tras TIME segundos |
| `-l LIST` | Conjunto de caracteres |
| `-u CHARS` | Caracteres personalizados |

## Cambios respecto al original

1. Se añadieron dos pares de color (`init_pair(4, ...)` cian y `init_pair(5, ...)` magenta).
2. Se añadió el método `two_color(x)` que devuelve aleatoriamente uno de los dos colores.
3. El default de velocidad pasó de `85` a `95`.
4. El set de caracteres por defecto pasó de `knnssss` a `katakana + klingon pIqaD` (`kP`).
