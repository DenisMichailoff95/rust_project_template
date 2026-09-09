# rust_project_template

Порядок работы при копировании шаблона в новый проект:

Запустить workspace: generate → создаётся rust.code-workspace с именем папки
Запустить template: configure → в launch.json подставляется реальное имя пакета из Cargo.toml
launch.json использует плейсхолдер __PACKAGE_NAME__, который заменяется на имя пакета.
