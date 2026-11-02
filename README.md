# Proyecto 2 – Redes (CIIC4070/ICOM5026): Configuración del entorno en Mac

## 1. Instalar Python e iperf3 con Homebrew

```bash
brew install python
brew install iperf3
```

## 2. Crear el entorno virtual dentro del proyecto (solo la primera vez)

El Python de Homebrew no permite `pip install` global (error *externally-managed-environment*), así que se usa un entorno virtual **dentro de la carpeta del proyecto**:

```bash
cd ruta/a/networks/Projecto2
python3 -m venv .venv
source .venv/bin/activate
python -m pip install notebook ipywidgets ipykernel
```

> Truco: escribe `cd ` y arrastra la carpeta `Projecto2` desde Finder a la terminal.

Verificar que quedó bien:

```bash
ls -a                       # debe aparecer .venv junto al .ipynb
.venv/bin/python --version  # debe mostrar Python 3.x
```

Si se activó bien, verás `(.venv)` al principio de la línea de la terminal.

## 3. Abrir el notebook

### Opción A: VS Code (recomendado)

No hace falta activar el entorno en la terminal: VS Code lo usa directamente como kernel.

1. Instala las extensiones **Python** y **Jupyter** (de Microsoft) con `Cmd + Shift + X`.
2. Desde la terminal, dentro de `Projecto2`:
   ```bash
   code .
   ```
   > Si sale `command not found: code`: en VS Code, `Cmd + Shift + P` → **Shell Command: Install 'code' command in PATH**.
3. Abre `stop_n_wait.ipynb` → **Select Kernel** → **Python Environments** → **.venv**.
4. **Run All** para ejecutar todas las celdas.

VS Code recuerda el kernel elegido para ese archivo.

### Opción B: Navegador

Cada vez que abras una terminal nueva:

```bash
cd ruta/a/networks/Projecto2
source .venv/bin/activate
jupyter notebook
```

