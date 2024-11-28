Estrutura do Repositório AS1
Diretórios e Arquivos Necessários
plaintext
Copiar código
AS1/
├── lib/
│   ├── main.dart
├── pubspec.yaml
└── README.md
Código do Arquivo main.dart (para lib/main.dart):
dart
Copiar código
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'AS1',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        brightness: Brightness.light,
      ),
      darkTheme: ThemeData(
        brightness: Brightness.dark,
      ),
      home: HomePage(),
    );
  }
}

class HomePage extends StatefulWidget {
  @override
  _HomePageState createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  final List<String> _tasks = [];
  final TextEditingController _controller = TextEditingController();

  void _addTask() {
    if (_controller.text.isNotEmpty) {
      setState(() {
        _tasks.add(_controller.text);
      });
      _controller.clear();
    }
  }

  void _removeTask(int index) {
    setState(() {
      _tasks.removeAt(index);
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('AS1 - Gerenciador de Tarefas'),
      ),
      body: Padding(
        padding: const EdgeInsets.all(16.0),
        child: Column(
          children: [
            TextField(
              controller: _controller,
              decoration: InputDecoration(
                labelText: 'Nova Tarefa',
                suffixIcon: IconButton(
                  icon: Icon(Icons.add),
                  onPressed: _addTask,
                ),
              ),
            ),
            SizedBox(height: 20),
            Expanded(
              child: ListView.builder(
                itemCount: _tasks.length,
                itemBuilder: (context, index) {
                  return ListTile(
                    title: Text(_tasks[index]),
                    trailing: IconButton(
                      icon: Icon(Icons.delete),
                      onPressed: () => _removeTask(index),
                    ),
                  );
                },
              ),
            ),
          ],
        ),
      ),
    );
  }
}
Código do Arquivo pubspec.yaml:
yaml
Copiar código
name: as1
description: A simple task management app using Flutter.
publish_to: "none"
version: 1.0.0+1

environment:
  sdk: ">=2.17.0 <3.0.0"

dependencies:
  flutter:
    sdk: flutter

dev_dependencies:
  flutter_test:
    sdk: flutter

flutter:
  uses-material-design: true
Código do Arquivo README.md:
markdown
Copiar código
# AS1 - Gerenciador de Tarefas

**AS1** é um aplicativo simples de gerenciamento de tarefas, ideal para aprender Flutter ou gerenciar atividades diárias de forma prática.

---

## 📋 Funcionalidades

- Adicionar tarefas à lista.
- Excluir tarefas da lista.
- Interface clara e responsiva.
- Suporte a tema claro e escuro.

---

## 🛠️ Tecnologias Utilizadas

- **Flutter**: Framework principal.
- **Dart**: Linguagem utilizada.
- **Material Design**: Interface baseada no Material Design.

---

## ⚙️ Como Executar o Projeto

### Requisitos:

Certifique-se de ter:

1. [Flutter SDK](https://docs.flutter.dev/get-started/install)
2. Um editor de código (VS Code ou Android Studio)
3. Emulador ou dispositivo físico conectado.

### Passo a Passo:

1. Clone o repositório:

```bash
git clone https://github.com/seuusuario/as1.git
cd as1
Instale as dependências:
bash
Copiar código
flutter pub get
Inicie o aplicativo:
bash
Copiar código
flutter run
📦 Estrutura de Arquivos
lib/main.dart: Código principal do aplicativo.
pubspec.yaml: Arquivo de configuração e dependências do projeto.
README.md: Documentação do projeto.
🤝 Contribuições
Contribuições são bem-vindas! Para colaborar:

Faça um fork do repositório.
Crie uma branch com sua contribuição (git checkout -b minha-feature).
Commit suas mudanças (git commit -m "Descrição da mudança").
Envie para o repositório (git push origin minha-feature).
Abra um Pull Request para revisão.
📜 Licença
Este projeto está licenciado sob a licença MIT.

📞 Contato
Email: marcos@gmail.com
GitHub: github.com/marcosqrocha
LinkedIn: linkedin.com/in/marcos
Desfrute de um aplicativo simples e funcional
