# TRABALHO 01:  Título do Trabalho

# Sumário

### 1. COMPONENTES<br>
Rafael Barbosa Martins: rafaelmartinscouto@gmail.com<br>
Pedro Ramos Leite Soares: pedro05042006@gmail.com<br>
João Pedro Zamborlini Barcellos: jpzbarcellos@gmail.com<br>
Gustavo Alves Caetano: gustavo.gustavovat@gmail.com<br>
<br>

### 2. INTRODUÇÃO E MOTIVAÇÃO<br>
> A empresa “FPS Solutions Ltda”, visa vender componentes relacionados a tecnologias. Sabendo a importância de um gerenciamento econômico e lógico, preciso e rápido, desenvolveremos um sistema de vendas, “FPSystem”. Nosso sistema tem o objetivo de gerenciar as informações de venda dos produtos, visando o comprador, distribuidora, transporte e o próprio produto, além de armazená-las. O sistema gerará um conjunto de relatórios que atenderá as necessidades da empresa.
 
### 3. MINI-MUNDO<br>
> O sistema proposto para a “FPS Solutions Ltda” conterá informações aqui detalhadas. Dos PRODUTOS serão armazenados o código, nome, marca e modelo. Das PESSOAS serão armazenados o código, nome, endereço e contato. Uma pessoa pode fornecer nenhum ou vários produtos, e um produto será fornecido por uma ou várias pessoas. Será armazenado sobre a distribuição, o preço do produto unitário distribuído, comissão em porcentagem para se aplicar ao produto e quantidade distribuída. Uma pessoa fará nenhum ou vários PEDIDOS e um pedido pertencerá a uma única pessoa, do pedido será armazenado a sua data e código. Um pedido possuirá um ou vários produtos, e um produto será possuído por nenhum ou vários pedidos, será armazenado sobre a posse a quantidade possuída do produto. Dos ENTREGADORES serão armazenados cpf, nome, telefone e salário. Um entregador transportará um ou vários produtos e um produto será transportado por exclusivamente um entregador. Sobre a entrega serão armazenados a data de chegada e o preço do frete. Dos VEÍCULOS serão armazenados código, placa e modelo, um veículo será usado por nenhum ou vários entregadores, e um entregador usará um ou vários veículos.

### 4. PERGUNTAS A SEREM RESPONDIDAS E TABELA DE DADOS<br>
    
> A Empresa FPS Solutions Ltda precisa inicialmente dos seguintes relatórios:
* Relatório para controle de estoque, que mostre para determinado produto, a quantidade do produto em estoque e o valor somado de todos os mesmos produtos (escala do valor somado 1:100).
* Relatório para controle financeiro, que mostre para determinado período, o capital gerado por todas as vendas (frete + comissão).
* Relatório para controle financeiro, que mostre para determinado período, lucro((frete + comissão) - gasto mensal com salários)
* Relatório para controle de vendas, que mostre para determinado estado a quantidade de produtos vendidos.
* Relatório para controle de pátio, que mostre para determinado marca, o número de carros da mesma.

 ### 5. MODELO CONCEITUAL<br>
 
![alt text](https://user-images.githubusercontent.com/91470894/199119581-5c239633-d4b6-4887-9e60-527179529513.png)

#### 5.1 Validação do Modelo Conceitual
> Grupo 01: Gabriel De Paulo Brunetti, Halisson Júlio Lopes. <br>
> Grupo 02: Caio Fraga Cintra, Ricardo Leite.

#### 5.2 Descrição dos dados 

> ENDERECO: Tabela que armazena as informações relativas ao endereço.
codigo: Número identificador.
tipo_logradouro: Tipo do logradouro, exemplos: rua, avenida…
descricao_logradouro: Nome do logradouro, exemplo: germano nauman.
numero: Número do endereço, exemplos: 01, 22, 13.
cidade: Cidade do endereço, exemplos: Serra, Colatina…
estado: Estado do endereço, exemplos: ES, RJ, SP…

> CONTATO: Tabela que armazena as informações relativas ao contato.
codigo: Número identificador.
descricao: O contato em si da pessoa, exemplos: 27997803226, rafael@gmail.com.

> TIPO_CONTATO: Tabela que armazena as informações relativas ao tipo do contato.
codigo: Número identificador.
nome: Nome do tipo do contato, exemplos: telefone, email, instagram.

> PESSOA: Tabela que armazena as informações relativas à pessoa.
codigo: Número identificador.
nome: Nome completo da pessoa, exemplo: Rafael Barbosa Martins.

> PRODUTO: Tabela que armazena as informações relativas ao produto.
codigo: Número identificador.
nome: Nome do produto, exemplos: RTX590,  Fonte Tomahawk 500wts.
modelo: Modelo do produto, exemplos: Hero, Cloud, Prime.

> PEDIDO: Tabela que armazena as informações relativas ao pedido.
codigo: Número identificador.
data_compra: Data da efetuação do pedido, exemplo: ‘2022-04-20 12:30:56’

> MARCA: Tabela que armazena as informações de marcas relativas ao produto e veículos.
codigo: Número identificador.
nome: Nome da empresa/marca, exemplos: Nvidia, Samsung.

> VEICULO: Tabela que armazena as informações relativas ao veículo.
codigo: Número identificador.
placa: Armazena a placa de identificação de trânsito de um carro, exemplos: PPH-3709, IJK-1168.

> MODELO: Tabela que armazena as informações de modelo relativas ao veículo.
codigo: Número identificador.
descricao: Descrição do modelo do veículo, exemplos: Biz 110i, Sprinter.

> ENTREGADOR: Tabela que armazena as informações relativas ao entregador.
codigo: Número identificador.
nome: Nome completo do entregador, exemplo: Rafael Barbosa Martins.
telefone: Telefone do entregador, exemplo: 997803226.
salario: Salário mensal do entregador, exemplo: 2000.

> CONTATO/PESSOA (Pertence): Relação entre contato e pessoa, em que um contato pertence a exclusivamente uma pessoa, e uma pessoa terá um ou vários contatos.

> CONTATO/TIPO_CONTATO (Possui): Relação entre contato e tipo de contato, em que um contato possui exclusivamente um tipo, e um tipo de contato pertencera a um ou vários contatos.

> ENDERECO/PESSOA (Pertence): Relação entre endereço e pessoa, em que um endereço pertence a uma ou várias pessoas e uma pessoa terá exclusivamente um endereço.

> PESSOA/PRODUTO(Distribui): Relação entre pessoa e produto, em que nenhuma ou várias pessoas distribuem um produto, é um produto e distribuído por uma ou várias pessoas. Serão armazenados sobre a distribuição:
comissao: Porcentagem que será aplicado sobre o produto, para lucro da empresa, exemplo: 20.
preco_unitario: Preço da unidade do produto, exemplo: 1500.
qtd: Quantidade daquele produto que foi distribuído, exemplo: 100.

> PESSOA/PEDIDO (Faz): Relação entre pessoa e pedido, em que uma pessoa faz nenhum ou vários pedidos, e um pedido será feito exclusivamente por uma pessoa.

> PEDIDO/PRODUTO (Possui): Relação entre pedido e produto, em que um pedido possuirá um ou vários produtos, e um produto será possuído por nenhum ou vários pedidos. Serão armazenados sobre a posse:
qtd: Quantidade daquele produto que o pedido possuirá, exemplos: 2, 5.

> ENTREGADOR/PRODUTO(Entrega): Relação entre entregador e produto, em que exclusivamente um entregador entregará o produto, e um ou vários produtos será entregue por um entregador. Serão armazenados sobre a entrega:
data_chegada: Data/hora da chegada do produto ao cliente, exemplo: 2022-04-23 17:10:56.
frete: Preço da entrega do produto, exemplo: 130.

> ENTREGADOR/VEICULO(Dirige): Relação entre entregador e veículo, em que um entregador dirige um ou vários veículos, e um veículo e dirigido por nenhum ou vários entregadores.

> VEICULO/MARCA(Produzido) e PRODUTO/MARCA(Produzido): Relação entre objeto e marca, em que um objeto é produzido por exclusivamente uma marca, uma marca pode produzir nenhum ou vários objetos.

> VEICULO/MODELO(Possui): Relação entre veículo e modelo, em que um veículo possui exclusivamente um modelo, e um modelo pode ser possuído por um ou vários veículos.

### 6.	MODELO LÓGICO<br>

![alt text](https://user-images.githubusercontent.com/91470894/199119195-42a85f1b-9e9c-4ea5-83d6-79fb03d7420b.png)

### 7.	MODELO FÍSICO<br>
    drop table if exists pessoa, contato, tipo_contato, pedido_produto, produto, entregador, veiculo, distribuidora_produto, pedido, entregador_veiculo, modelo,           marca, endereco, entrega CASCADE;

    create table tipo_contato (
    codigo integer primary key,
    nome varchar(30)
    );

    create table contato (
    codigo integer primary key,
    descricao varchar(40),
    fk_cod_tipo_contato integer,
    fk_cod_pessoa integer
    );


    create table endereco(
    codigo integer primary key,
    tipo_logradouro varchar(10),
    descricao_logradouro varchar(50),
    numero integer,
    cidade varchar(30),
    estado varchar(3)
    );

    create table pessoa(
    codigo integer primary key,
    fk_cod_endereco integer references endereco (codigo),
    nome varchar(45)
    );

    create table modelo(
    codigo integer primary key,
    descricao varchar(45)
    );

    create table marca(
    codigo integer primary key,
    nome varchar(30)
    );

    create table produto(
    codigo integer primary key,
    nome varchar(30),
    fk_cod_marca integer references marca(codigo),
    modelo varchar(40)
    );

    create table entregador(
    fk_codigo_pessoa integer references pessoa(codigo),
    salario float
    );

    create table veiculo(
    codigo integer primary key,
    placa varchar(8),
    fk_cod_modelo integer references modelo(codigo),
    fk_cod_marca integer references marca(codigo)
    );

    create table distribuidora_produto(
    fk_codigo_pessoa integer references pessoa (codigo),
    fk_codigo_produto integer references produto(codigo),
    preco_unidade float,
    comissao float,
    qtd integer
    );

    create table pedido(
    codigo integer primary key,
    fk_codigo_cliente integer references pessoa(codigo),
    fk_codigo_entregador integer references pessoa(codigo),
    data_compra timestamp
    );

    create table pedido_produto (
    fk_codigo_pedido integer references pedido (codigo),
    fk_codigo_produto integer references produto (codigo),
    qtd integer
    );

    create table entrega(
    codigo integer primary key,
    data_chegada timestamp,
    frete float,
    fk_cod_pedido integer references pedido (codigo) 
    );

    create table entregador_veiculo(
    fk_codigo_pessoa integer references pessoa(codigo),
    fk_codigo_veiculo integer references veiculo(codigo) 
    );        
       
### 8.	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
    insert into tipo_contato (codigo, nome) values 
    (1, 'email' ), 
    (2, 'telefone'), 
    (3, 'instagram');

    insert into contato (codigo, descricao, fk_cod_tipo_contato, fk_cod_pessoa) values 
    (1, 'kamilly@gmail.com', 1, 1),
    (2, '92441728', 2, 2),
    (3, '92745638', 2, 3),
    (4, '99725474', 2, 4),
    (5, '88446214', 2, 5),
    (6, '78546042', 2, 6),
    (7, '98421487', 2, 7),
    (8, '01929854', 2, 8),
    (9, '98216712', 2, 9),
    (10,'cadura.jotinha', 3, 10),
    (11, 'ev7.oficial', 3, 11),
    (12, 'anderson@gmail.com', 1, 12),
    (13, 'cassino', 3, 13),
    (14, '998726456', 2, 14),
    (15, '990876432', 2, 15),
    (16,  'kabum@gmail.com', 1, 28),
    (17, 'pichau@gmail.com', 1, 29),
    (18, 'mistica@gmail.com', 1, 30),
    (19, '21781939', 2, 16),
    (20, '33733277', 2, 17),
    (21, '31162607', 2, 18),
    (22, 'rogercalvoguedes@gmail.com', 1, 19),
    (23, '24885641', 2, 20),
    (24, '36704395', 2, 21),
    (25, '34786188', 2, 22),
    (26, '34354453', 2, 23),
    (27, '26438865', 2, 24),
    (28, '33784168', 2, 25),
    (29, '37456607', 2, 26),
    (30, '21716600', 2, 27),
    (31, '86388259', 2, 12),
    (32, '26963441', 2, 22),
    (33, '73139367', 2, 21),
    (34,'tmaia@gmail.com', 1, 25),
    (35, '78458268', 2, 15),
    (36, '60594251', 2, 3),
    (37, '27594680', 2, 17),
    (38, '85251508', 2, 11),
    (39, '68011031', 2, 29),
    (40, '51635348', 2, 28),
    (41, '96343070', 2, 29),
    (42, '81269103', 2, 11),
    (43, '32965605', 2, 10),
    (44,'is@dor@.lun@', 3, 8),
    (45, '23934046', 2, 2),
    (46, '97214676', 2, 14),
    (47, '41393409', 2, 26),
    (48, '89704601', 2, 22),
    (49, '36000208', 2, 8),
    (50, '81799453', 2, 11);


     insert into endereco (codigo, tipo_logradouro, descricao_logradouro, numero, cidade, estado) values
     (1, 'Rua', 'Arlindo Carneiro', 1234512, 'Poços de Caldas', 'MG'),
     (2, 'Rua', 'Jornalista José Lopes dos Santos', 2345623, 'Teresina', 'PI'),
     (3, 'Rua', 'Emília Michalski Ubá', 3456734, 'Curitiba', 'PR'),
     (4, 'Rua', 'Calcutá', 45678-45, 'Manaus', 'AM'),
     (5, 'Alameda', 'Tarumã', 5678956, 'Macapá', 'AP'),
     (6, 'Rua', 'Tenente Severino Pereira', 6789067, 'Bayeux', 'PB'),
     (7, 'Rua',  'Luiza Batista Guedes', 3193030, 'Belo Horizonte', 'MG'),
     (8, 'Rua', 'Praia do Sobral',  59094140, 'Natal', 'RN'),
     (9, 'Viela', 'SC 11 A', 74860440, 'Goiânia', 'GO'),
     (10, 'Rua', 'Antônio Bueno de Carvalho', 0623310, 'Osasco', 'SP'),
     (11 ,'Rua', 'Frutuoso Borges Fontoura', 56723809, 'Cachoeira do sul', 'RS'),
     (12, 'Rua', 'Travessa Feijó', 3897682, 'Rio Branco', 'AC'), 
     (13, 'Avenida', 'Talma Rodrigues', 29167920, 'São Paulo', 'SP'),
     (14, 'Rua', 'Antônio Bueno de Carvalho', 0623310, 'Osasco', 'SP'),
     (15, 'Rua', 'Biguás', 1243, 'Serra', 'ES'),
     (16, 'Rua', 'Jornalista José Lopes dos Santos', 2345623, 'Teresina', 'PI');

     insert into pessoa(codigo, fk_cod_endereco, nome) values
     (1, 14, 'Kamilly Mariah Carolina Nunes'),
     (2, 8, 'Róger Krug Guedes'),
     (3, 13, 'Neymar da Silva Santos Júnior'),
     (4, 12, 'Sandra Sophie Rafaela Silva'),
     (5, 5, 'Eduardo Nascimento da Silva Júnior'),
     (6, 1, 'Vicente de Paula Brunetti'),
     (7, 8, 'Janeiro Fevereiro de Março Abril'),
     (8, 3, 'Isadora Luna Isabelly Barbosa'),
     (9, 11, 'Ryan Anthony Fernandes'),
     (10, 4, 'Giuseph Cadura'),
     (11, 7, 'Éverton Ribeiro'),
     (12, 6, 'Anderson Luiz de Carvalho'),
     (13, 1, 'Gilberto Barros'),
     (14, 12, 'Henrique Caio Almeida'),
     (15, 10, 'Gabriel Barbosa'),
     (16, 14, 'Pedro Guilherme'),
     (17, 4, 'Giorgian de Arrascaeta'),
     (18, 11, 'Éverton Cebolinha'),
     (19, 13, 'Goleiro Santos'),
     (20, 8, 'Filipe Luíz'),
     (21, 16, 'David Luíz'),
     (22, 16, 'Léo Pereira'),
     (23, 13, 'Rodilindo'),
     (24, 9, 'Matheus França'),
     (25, 7, 'Thiago Maia'),
     (26, 14, 'João Gomes'),
     (27, 13, 'Arturo Vidal'),
     (28, 14, 'Kabum'),
     (29, 14, 'Pichau'),
     (30, 3, 'Mistica');



     insert into marca(codigo, nome) values
     (1, 'Asus'),
     (2, 'Honda'),
     (3,  'Nvidia'),
     (4, 'Samsung'),
     (5, 'T-Dagger'),
     (6,  'Logitech'),
     (7,  'Kingston'),
     (8, 'HyperX'),
     (9,  'Multilaser'),
     (10, 'Team Group Pichau Delta'),
     (11,  'TGT'),
     (12, 'Mercedes-Benz'),
     (13, 'Redragon'),
     (14, 'MoobX'),
     (15, 'PowerA'),
     (16, 'Espresso Móveis'),
     (17, 'Volkswagen'),
     (18, 'Chevrolet'),
     (19, 'Trust');

     insert into entregador(fk_codigo_pessoa, salario) values
     (18, 1400.00),
     (19, 1600.00),
     (20, 1437.00),
     (21, 1572.00),
     (22, 1398.00),
     (23, 1597.00),
     (24, 1981.00),
     (25, 1326.00),
     (26, 1789.00),
     (27, 1570.00);

     insert into modelo(codigo, descricao)values
     (1, 'Biz 110i'),
     (2, 'Pop 110i'),
     (3, 'Sprinter'),
     (4, 'Saveiro'),
     (5, 'Celta');

     insert into veiculo(codigo, placa, fk_cod_modelo, fk_cod_marca) values
     (1, 'PAB-5403', 1, 2),
     (2, 'FPZ-6969', 1, 2),
     (3, 'CWK-5617', 2, 2),
     (4, 'EBB-6885', 2, 2),
     (5, 'RBU-8911', 1, 2),
     (6, 'CGO-4867', 2, 12),
     (7, 'FTW-3929', 2, 12),
     (8, 'NDB-6010', 2, 12),
     (9, 'FMC-6172', 4, 17),
     (10, 'MSW-3152', 4, 17),
     (11, 'GYR-8515', 5, 18),
     (12, 'MNR-5077', 5, 18);

     insert into entregador_veiculo(fk_codigo_pessoa , fk_codigo_veiculo) values
     (18, 1),
     (20, 3),
     (19, 5),
     (21, 7),
     (22, 8),
     (23, 11),
     (24, 5),
     (25,7),
     (27, 8),
     (26, 9),
     (18, 11);

     insert into produto(codigo, nome, fk_cod_marca, modelo) values
     (1, 'RTX 5090', 3, 'TI 24GB'),
     (2, 'Odyssey', 4, 'G9 120HZ'),
     (3, 'Bora', 5, 'T-TGK315'),
     (4, 'G403', 6, 'Hero'),
     (5, 'SSD A400', 7, 'SA400S37'),
     (6, 'Headset CloudX', 8, 'Cloud'),
     (7, 'Classic Box', 9, 'Óptico full black usb'),
     (8, 'Memória T-Force 16gb', 10, 'DDR4 3600mhz'),
     (9, 'Placa mãe H410M-E', 1, 'Prime'),
     (10, 'Fonte Tomahawk 500wts', 11, 'TMWK500'),
     (11, 'Water Cooler Spartel 240', 11, 'Rainbow 200mm'),
     (12, 'Gabinete Aurora', 4, 'Alienware R9'),
     (13, 'Mouse Gamer ', 6, 'G203'),
     (14, 'Mousepad Gamer ', 13, 'Aquarius'),
     (15, 'Microfone Gamer', 8, 'QuadCast'),
     (16, 'Webcam', 13, 'Hitman'),
     (17, 'Cadeira Gamer', 14 , 'GT RACER'),
     (18, 'Controle Infinity', 15, 'Spectra'),
     (19, 'Desk Gamer', 16, 'DRX 6000'),
     (20, 'Caixa de som GXT', 19, '619 Thor');

     insert into pedido(codigo, fk_codigo_cliente, fk_codigo_entregador, data_compra) values
     (1, 10, 26, '2022-1-25 15:42:18'),
     (2, 11, 27, '2022-1-29 6:20:4'),
     (3, 17, 27, '2022-2-20 5:27:28'),
     (4, 17, 24, '2022-3-11 13:35:17'),
     (5, 16, 19, '2022-3-23 17:52:31'),
     (6, 10, 20, '2022-3-6 19:22:23'),
     (7, 5, 26, '2022-1-3 10:10:7'),
     (8, 7, 23, '2022-1-10 10:48:12'),
     (9, 8, 18, '2022-2-25 13:18:54'),
     (10, 11, 19, '2022-3-11 11:34:42'),
     (11, 7, 23, '2022-6-2 18:39:29'),
     (12, 4, 25, '2022-5-4 14:40:16'),
     (13, 9, 27, '2022-6-5 19:11:1'),
     (14, 11, 26, '2022-4-4 19:4:41'),
     (15, 14, 19, '2022-4-17 7:40:54'),
     (16, 12, 19, '2022-6-21 8:8:28'),
     (17, 13, 23, '2022-6-1 20:19:19'),
     (18, 8, 22, '2022-4-6 1:49:25'),
     (19, 17, 22, '2022-5-27 5:13:15'),
     (20, 5, 25, '2022-5-19 2:48:56'),
     (21, 16, 19, '2022-4-28 10:14:54'),
     (22, 4, 19, '2022-7-20 13:28:2'),
     (23, 1, 21, '2022-8-9 2:54:53'),
     (24, 13, 18, '2022-10-19 22:32:17'),
     (25, 14, 20, '2022-8-8 4:6:11'),
     (26, 17, 24, '2022-7-9 12:46:25'),
     (27, 6, 22, '2022-10-7 9:56:21'),
     (28, 5, 19, '2022-7-6 11:56:39'),
     (29, 16, 20, '2022-8-11 14:50:28'),
     (30, 16, 25, '2022-8-16 5:47:36'),
     (31, 3, 21, '2022-10-12 16:50:48'),
     (32, 9, 21, '2022-12-4 8:15:31'),
     (33, 4, 23, '2022-12-8 17:50:43'),
     (34, 15, 27, '2022-11-11 9:44:54'),
     (35, 3, 20, '2022-11-28 20:43:23'),
     (36, 13, 19, '2022-11-1 8:59:21'),
     (37, 6, 18, '2022-12-24 20:16:3'),
     (38, 13, 23, '2022-12-14 14:17:58'),
     (39, 1, 21, '2022-12-23 18:32:46'),
     (40, 13, 21, '2022-11-8 21:16:21'),
     (41, 4, 25, '2022-11-11 9:5:32'),
     (42, 2, 18, '2023-1-28 15:21:14'),
     (43, 14, 22, '2023-3-27 6:59:49'),
     (44, 12, 18, '2023-1-22 22:4:25'),
     (45, 12, 20, '2023-1-4 20:20:7'),
     (46, 17, 27, '2023-3-19 21:25:42'),
     (47, 6, 19, '2023-3-14 20:3:8'),
     (48, 16, 27, '2023-3-17 18:18:46'),
     (49, 9, 25, '2023-2-23 18:27:12'),
     (50, 4, 27, '2023-3-8 3:34:22');

     insert into pedido_produto (fk_codigo_pedido, fk_codigo_produto, qtd) values
     (1, 3, 4),
     (2, 17, 1),
     (3, 8, 1),
     (4, 10, 2),
     (5, 19, 4),
     (6, 4, 2),
     (7, 15, 4),
     (8, 8, 2),
     (9, 12, 4),
     (10, 3, 3),
     (11, 9, 4),
     (12, 6, 3),
     (13, 1, 1),
     (14, 7, 3),
     (15, 9, 1),
     (16, 5, 3),
     (17, 9, 3),
     (18, 15, 1),
     (19, 8, 1),
     (20, 4, 4),
     (21, 8, 4),
     (22, 20, 1),
     (23, 2, 2),
     (24, 12, 4),
     (25, 12, 3),
     (26, 20, 2),
     (27, 4, 1),
     (28, 13, 3),
     (29, 12, 1),
     (30, 16, 2),
     (31, 5, 3),
     (32, 18, 1),
     (33, 18, 4),
     (34, 3, 1),
     (35, 2, 4),
     (36, 1, 1),
     (37, 17, 3),
     (38, 3, 3),
     (39, 4, 1),
     (40, 6, 3),
     (41, 5, 3),
     (42, 1, 4),
     (43, 4, 2),
     (44, 6, 2),
     (45, 10, 1),
     (46, 9, 2),
     (47, 20, 2),
     (48, 18, 4),
     (49, 14, 3),
     (50, 4, 1),
     (1, 16, 4),
     (2, 9, 2),
     (3, 11, 4),
     (4, 17, 2),
     (5, 17, 3),
     (6, 6, 2),
     (7, 8, 1),
     (8, 1, 4),
     (9, 5, 4),
     (10, 19, 3),
     (11, 9, 1),
     (12, 11, 3),
     (13, 3, 1),
     (14, 10, 3),
     (15, 1, 2),
     (16, 18, 1),
     (17, 5, 3),
     (18, 12, 3),
     (19, 20, 2),
     (20, 6, 1),
     (21, 13, 1),
     (22, 3, 1),
     (23, 16, 1),
     (24, 16, 1),
     (25, 15, 1),
     (26, 13, 1),
     (27, 12, 3),
     (28, 11, 3),
     (29, 1, 2),
     (30, 17, 4),
     (31, 18, 4),
     (32, 17, 2),
     (33, 7, 3),
     (34, 6, 3),
     (35, 20, 3),
     (36, 5, 3),
     (37, 15, 4),
     (38, 12, 1),
     (39, 4, 2),
     (40, 6, 4),
     (41, 16, 1),
     (42, 4, 3),
     (43, 5, 2),
     (44, 2, 4),
     (45, 4, 3),
     (46, 18, 2),
     (47, 10, 1),
     (48, 3, 4),
     (49, 18, 3),
     (50, 20, 2);



     insert into entrega(codigo, data_chegada, frete, fk_cod_pedido) values
     (1, '2022-5-17 20:41:33', 53.57, 1),
     (2, '2022-4-13 7:4:58', 96.22, 2),
     (3, '2022-5-23 15:32:34', 114.68, 3),
     (4, '2022-4-20 14:11:59', 92.39, 4),
     (5, '2022-4-21 7:56:34', 42.72, 5),
     (6, '2022-6-17 18:7:43', 48.96, 6),
     (7, '2022-4-5 11:11:9', 109.44, 7),
     (8, '2022-4-9 6:34:16', 83.46, 8),
     (9, '2022-4-26 15:41:55', 83.39, 9),
     (10, '2022-5-1 16:24:59', 43.38, 10),
     (11, '2022-7-24 13:48:31', 107.93, 11),
     (12, '2022-9-11 9:42:47', 48.53, 12),
     (13, '2022-8-24 13:4:33', 105.63, 13),
     (14, '2022-7-17 2:16:14', 55.56, 14),
     (15, '2022-7-19 3:2:10', 105.08, 15),
     (16, '2022-9-6 13:46:49', 52.16, 16),
     (17, '2022-7-1 7:9:27', 129.02, 17),
     (18, '2022-8-5 8:27:31', 112.22, 18),
     (19, '2022-9-22 16:24:52', 77.49, 19),
     (20, '2022-8-18 14:25:59', 45.77, 20),
     (21, '2022-10-23 10:57:46', 106.95, 21),
     (22, '2022-11-10 18:28:6', 86.07, 22),
     (23, '2022-10-21 7:7:10', 110.91, 23),
     (24, '2022-10-17 9:4:57', 44.44, 24),
     (25, '2022-11-29 8:37:42', 111.17, 25),
     (26, '2022-10-25 18:14:44', 91.39, 26),
     (27, '2022-10-19 16:32:23', 97.79, 27),
     (28, '2022-10-14 20:56:2', 40.18, 28),
     (29, '2022-10-14 19:39:54', 92.36, 29),
     (30, '2022-10-10 3:41:40', 124.94, 30),
     (31, '2023-3-27 19:22:26', 74.58, 31),
     (32, '2023-3-21 2:15:54', 128.37, 32),
     (33, '2023-3-28 17:23:14', 42.19, 33),
     (34, '2023-2-23 4:32:33', 113.47, 34),
     (35, '2023-2-21 21:1:46', 90.99, 35),
     (36, '2023-2-26 22:51:21', 112.30, 36),
     (37, '2023-3-22 1:1:3', 51.02, 37),
     (38, '2023-1-26 12:44:14', 66.08, 38),
     (39, '2023-1-27 14:27:40', 88.99, 39),
     (40, '2023-2-17 18:14:57', 123.82, 40),
     (41, '2023-4-22 16:37:17', 97.53, 41),
     (42, '2023-4-17 21:48:54', 100.14, 42),
     (43, '2023-4-22 16:55:4', 117.00, 43),
     (44, '2023-5-4 12:37:9', 118.35, 44),
     (45, '2023-6-5 10:39:5', 124.00, 45),
     (46, '2023-5-9 4:48:35', 117.40, 46),
     (47, '2023-6-11 6:52:46', 101.80, 47);


     insert into distribuidora_produto(fk_codigo_pessoa, fk_codigo_produto, preco_unidade, comissao, qtd) values
     (30, 6, 339.99, 0.04, 20),
     (29, 2, 1249.99, 0.02, 40),
     (30, 12, 889.90, 0.06, 35),
     (30, 5, 798.90, 0.08, 60),
     (28, 17, 900.00, 0.08, 15),
     (29, 7, 10.90, 0.10, 20),
     (30, 8, 399.90, 0.09, 90),
     (30, 16, 935.99, 0.07, 70),
     (30, 20, 300.00, 0.10, 20),
     (28, 2, 349.90, 0.10, 22),
     (28, 8, 329.90, 0.01, 33),
     (28, 17, 939.90, 0.09, 66),
     (29, 9, 670.90, 0.10, 76),
     (29, 7, 8.00, 0.10, 27),
     (29, 11, 450.00, 0.03, 30),
     (30, 19, 555.90, 0.04, 55),
     (28, 18, 499.99, 0.08, 69),
     (30, 3, 274.90, 0.04, 17),
     (29, 9, 590.90, 0.04, 13),
     (30, 11, 524.99, 0.07, 22),
     (30, 14,159.90, 0.01, 49),
     (30, 6, 369.90, 0.11, 22),
     (29, 10, 129.90, 0.09, 29),
     (30, 15, 790.90, 0.03, 33),
     (28, 16, 429.90, 0.09, 90),
     (30, 14, 100.00, 0.11, 87),
     (28, 4, 229.80, 0.08, 69),
     (29, 10,140.00, 0.04, 66),
     (30, 1, 15998.90, 0.10, 77),
     (29, 13, 99.90, 0.11, 7);

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    https://colab.research.google.com/drive/1yiOFAjaPF73vdO5bcE9n537k4vgPwaAF?usp=sharing

#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas

#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.

#### 9.5	INSTRUÇÕES APLICANDO ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
    a) Criar minimo 3 de exclusão
    b) Criar minimo 3 de atualização

#### 9.6	CONSULTAS COM INNER JOIN E ORDER BY (Mínimo 6)<br>
    a) Uma junção que envolva todas as tabelas possuindo no mínimo 2 registros no resultado
    b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho

#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>
    a) Criar minimo 2 envolvendo algum tipo de junção

#### 9.8	CONSULTAS COM LEFT, RIGHT E FULL JOIN (Mínimo 4)<br>
    a) Criar minimo 1 de cada tipo

#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join (caso não ocorra na base justificar e substituir por uma view)
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho

#### 9.10	SUBCONSULTAS (Mínimo 4)<br>
     a) Criar minimo 1 envolvendo GROUP BY
     b) Criar minimo 1 envolvendo algum tipo de junção

># Marco de Entrega 02: Do item 9.2 até o ítem 9.10<br>

### 10 RELATÓRIOS E GRÁFICOS (Usar template disponibilizado)
[Colab relatórios](https://colab.research.google.com/drive/1yiOFAjaPF73vdO5bcE9n537k4vgPwaAF?usp=sharing "Colab Relatórios")

#### a) análises e resultados provenientes do banco de dados desenvolvido (usar modelo disponível)
#### b) link com exemplo de relatórios será disponiblizado pelo professor no AVA
#### OBS: Esta é uma atividade de grande relevância no contexto do trabalho. Mantenha o foco nos 5 principais relatórios/resultados visando obter o melhor resultado possível.

    

### 11	AJUSTES DA DOCUMENTAÇÃO, CRIAÇÃO DOS SLIDES E VÍDEO PARA APRESENTAÇAO FINAL <br>

#### a) Modelo (pecha kucha)<br>
https://docs.google.com/presentation/d/1M2XKTkSe55xf3HXwGlgPy2tkmD-5F3QRKm061OzroZw/edit#slide=id.g1427d2c2c71_0_2411
#### b) Tempo de apresentação 6:40 

># Marco de Entrega 03: Itens 10 e 11<br>
<br>
<br>
<br> 



### 12 FORMATACAO NO GIT:<br> 
https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
    
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/
#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

    
### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. <strong>Caso existam arquivos com conteúdos sigilosos<strong>, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário do git "profmoisesomena", para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://www.sis4.com/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


