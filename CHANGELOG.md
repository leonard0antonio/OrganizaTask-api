# Changelog

All notable changes to this project will be documented in this file. See [commit-and-tag-version](https://github.com/absolute-version/commit-and-tag-version) for commit guidelines.

## [1.1.0](https://github.com/leonard0antonio/task-manager-api/compare/v1.0.2...v1.1.0) (2026-05-20)


### ✨ Funcionalidades (Features)

* adiciona rota put para edicao completa de tarefas ([44c69cc](https://github.com/leonard0antonio/task-manager-api/commit/44c69cc9e89ac193045f69a89f12ed6d41d1417d))
* adiciona rotas para edicao e exclusao de times com trava de seguranca ([54e3f5c](https://github.com/leonard0antonio/task-manager-api/commit/54e3f5c206d1938eff2110eebce96cccbc532093))
* adiciona verificação de e-mail existente na criação de usuário ([4e121c1](https://github.com/leonard0antonio/task-manager-api/commit/4e121c1063c04d5a0c7149b6471a76124d05e722))
* aplica regras estritas de isolamento multi-tenant na listagem de tarefas ([88603ad](https://github.com/leonard0antonio/task-manager-api/commit/88603ad11898cb895c5ff85f26f3588ff1c3e730))
* aprimora a listagem de tarefas com segurança de workspace e validação de usuário ([d2bd382](https://github.com/leonard0antonio/task-manager-api/commit/d2bd382ec7d2aa58e1d1db1125b6ca1fe6e96414))
* cria rota exclusiva para admin cadastrar usuarios com isolamento ([29b77b9](https://github.com/leonard0antonio/task-manager-api/commit/29b77b9eb2b671fa2e3849d52570afe4e67c34f0))
* implementa funcao updateUser no controller de usuarios ([704e4ef](https://github.com/leonard0antonio/task-manager-api/commit/704e4ef546b3035d3b432dcbe9227d40ff90f68a))


### 🐛 Correções de Bugs (Bug Fixes)

* aplica isolamento multi-tenant na criacao e listagem de times ([682dbe7](https://github.com/leonard0antonio/task-manager-api/commit/682dbe75528a9a7e1a37357126098f93d57b44d0))
* remove variavel inexistente na desestruturacao do req.user ([14a3207](https://github.com/leonard0antonio/task-manager-api/commit/14a3207b69f6d0506fec2c197a64f7accdc5ce6d))


### ♻️ Refatoração de Código

* melhora a atualização de status da tarefa e ajusta as rotas de autenticação ([e832641](https://github.com/leonard0antonio/task-manager-api/commit/e832641ea70905617cb9ae60c4cdf1b3992020a7))

## [1.0.1](https://github.com/leonard0antonio/task-manager-api/compare/v1.0.0...v1.0.1) (2026-05-13)


### ♻️ Refatoração de Código

* isola exclusao e listagem de tarefas por admin ([c9ad06e](https://github.com/leonard0antonio/task-manager-api/commit/c9ad06e02801cbc5a6c7cf626fc4a0df4a2eacf3))

## 1.0.0 (2026-05-11)


### ✨ Funcionalidades (Features)

* adiciona arquivo de configuração para tipos de commit ([485f0bc](https://github.com/leonard0antonio/task-manager-api/commit/485f0bc0dde69a8a09c6f1cebc268e9b7d7e6980))
* adiciona relacionamentos de admin e membros no modelo de usuário ([84f0153](https://github.com/leonard0antonio/task-manager-api/commit/84f0153a7b40332789845060400b3d207476b9d5))
* adiciona rota para listar times ([d8b2769](https://github.com/leonard0antonio/task-manager-api/commit/d8b2769d068512d8ca53aab1c6979856c4800ec0))
* adiciona rota para listar usuarios no painel admin ([d839537](https://github.com/leonard0antonio/task-manager-api/commit/d8395370a09ff8bdb0a404806661036d11b47b7b))


### 🐛 Correções de Bugs (Bug Fixes)

* adiciona rota de criacao de times ([3d755e6](https://github.com/leonard0antonio/task-manager-api/commit/3d755e69ccee863df8bb296fd154c99c0398ec1e))
