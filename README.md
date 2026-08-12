# 🧪 LAB 05: Empacotamento Docker Multi-Stage Otimizado com Drivers NVIDIA CUDA

## 🎯 Objetivo do Lab
Aprender a isolar e empacotar servidores de inferência de IA em contêineres Docker de alta eficiência, reduzindo a superfície de ataque e o tamanho final da imagem.

---

## 📋 Pré-requisitos
- Ter concluído *Building Containerized Applications with Docker & K8s* (IBM).
- Docker Engine 24+, NVIDIA Container Toolkit.

---

## 🛠️ O que você deve construir neste Lab:

### Etapa 1: Dockerfile Multi-Stage Pro
1. Escreva um `Dockerfile` em duas etapas (Builder e Runner):
   - **Stage 1 (Builder):** Usa imagem base `nvidia/cuda:12.1.0-devel-ubuntu22.04` para compilar dependências Python.
   - **Stage 2 (Runner):** Usa imagem leve `nvidia/cuda:12.1.0-runtime-ubuntu22.04`, copiando apenas os artefatos compilados.
2. Reduza o tamanho final da imagem para menos de **2.0 GB**.

### Etapa 2: Docker Compose & Runtime GPU
1. Crie um arquivo `docker-compose.yml` que configure a alocação de GPUs NVIDIA no contêiner (`deploy.resources.reservations.devices`).

---

## ✅ Critérios de Aceitação & Entrega
- [ ] Imagem Docker construída via `docker build` sem rodar como usuário root.
- [ ] Teste do comando `nvidia-smi` dentro do contêiner retornando as informações da GPU host.
