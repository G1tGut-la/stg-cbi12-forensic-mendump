# Análisis de un Volcado de Memoria

## Descripción

Este repositorio contiene un análisis detallado de un volcado de memoria realizado en un sistema Debian 11. El objetivo es identificar artefactos y evidencias que puedan ser relevantes en una investigación de forénsica digital.

## Disclaimer

Proyecto de práctica académica para la **Universidad Internacional San Isidro Labrador**.

| Estudiante  | Gustavo Villanueva Sandi                                             |
|-------------|----------------------------------------------------------------------|
| Curso       | (CIB-12) Forénsica Digital                                           |
| Entregable  | Análisis de un volcado de memoria                                    |
| Profesor    | Saenz Córdoba Irvin Argenis                                          |
| Repositorio | [GitHub - stg-cbi12-forensic-mendump](https://github.com/G1tGut-la/stg-cbi12-forensic-mendump) |

## Archivos

- `README.md`: Documentación del proceso de análisis.

## OS de prueba

Debian 11.0 (Se tuvo que modificar la version de debian debido a que Volatility no es compatible con Debian en las versiones 11 en adelante por problemas de Kernel)

## Requerimientos

- Python 3 instalado.
- Git instalado.
- Completar el POC del repositorio [GitHub - stg-cbi10-os-raceVulnerability] (https://github.com/G1tGut-la/stg-cbi10-os-raceVulnerability)

## Instrucciones de Análisis (root)

1. **Instalar y Ejecutar LiME:**
   ```bash
   sudo apt install build-essential
   ```
    ```bash
   sudo apt install lime-forensics-dkms
   ```
   ```bash
   git clone https://github.com/504ensicsLabs/LiME.git
   ```
   ```bash
   cd LiME/src
   ```
   ```bash
   sudo make
   ```
   ```bash
   sudo insmod ./lime-your_kernel_version.ko "path=/root/dump.mem format=raw"
   ```

2. **Instalar y Ejecutar Volatility**
   ```bash
   sudo apt install -y python3-pip
   ```
   ```bash
   pip3 install volatility3
   ```
   ```bash
   git clone https://github.com/volatilityfoundation/volatility3.git
   ```
   ```bash
   ./vol.py -f /root/dump.mem banners.Banners
   ```

3. **Calcular Hash del Dump de memoria**
   ```bash
   sha256sum /root/dump.mem
   ```

## Video de Demostración

[Enlace al video de demostración aquí](video/MSIVirtualMachine.mp4)

---

**⚠ ADVERTENCIA:** Este código es solo para fines educativos. No utilizado en producción ni para actividades ilicitas.
