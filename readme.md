
# Desafio Terraform: Provisionando uma Máquina Virtual no Azure

Este repositório contém um desafio prático para quem deseja aprender a utilizar o **Terraform** para provisionar uma infraestrutura na nuvem **Azure**, especificamente criando uma Máquina Virtual (VM) Linux.

## Objetivo

O objetivo deste desafio é ajudar você a aprender como:
- Criar um grupo de recursos no Azure.
- Criar uma rede virtual e sub-rede.
- Criar uma máquina virtual com SSH configurado para acesso remoto.
- Utilizar Network Security Groups (NSGs) para permitir tráfego na porta 22 (SSH).

## Pré-requisitos

Antes de iniciar, você precisará:
- **Conta no Azure**: Uma conta gratuita ou paga no Microsoft Azure.
- **Terraform**: Verifique se o Terraform está instalado na sua máquina. Se não estiver, siga as instruções em [Terraform Install](https://learn.hashicorp.com/tutorials/terraform/install-cli).
- **Azure CLI**: Para se autenticar na sua conta do Azure via CLI. Você pode instalar a Azure CLI com:
    ```bash
    sudo apt-get update
    sudo apt-get install azure-cli
    ```

## Instruções

### 1. Clone este repositório

Primeiro, faça um clone deste repositório no seu ambiente local:

```bash
git clone https://github.com/seu-usuario/terraform-azure-vm.git
cd terraform-azure-vm
```

### 2. Configurar as variáveis do Terraform

Antes de começar, crie um arquivo chamado `terraform.tfvars` com as credenciais da sua assinatura do Azure:

```hcl
subscription_id = "SUA_SUBSCRIPTION_ID"
```

### 3. Inicializar o Terraform

Inicialize o Terraform para baixar os plugins e configurar o ambiente:

```bash
terraform init
```

### 4. Planejar e aplicar o Terraform

Para ver o que o Terraform vai provisionar, execute:

```bash
terraform plan
```

Em seguida, aplique as mudanças para criar a infraestrutura:

```bash
terraform apply
```

### 5. Acessar a Máquina Virtual

Após o provisionamento, o Terraform exibirá o **IP Público** da VM. Use o comando abaixo para se conectar via SSH:

```bash
ssh tfadmin@<IP_PÚBLICO>
```

Certifique-se de que sua chave SSH está configurada corretamente.

### 6. Destruir a infraestrutura (opcional)

Quando terminar, se você quiser destruir todos os recursos provisionados para evitar custos, execute:

```bash
terraform destroy
```

## Estrutura do Projeto

- **`main.tf`**: Contém a configuração principal de infraestrutura (Grupo de Recursos, VNet, Sub-rede, VM, IP Público, NSG).
- **`variables.tf`**: Definição das variáveis utilizadas no projeto, como subscription_id.
- **`terraform.tfvars`**: Arquivo onde você define valores sensíveis, como suas credenciais do Azure (adicionado ao `.gitignore`).

## Contribuições

Se identificar algum erro, melhoria ou apenas quiser deixar um feedback: gentiltechdf@gmail.com

