- ts.createLanguageService()
- service.getProgram()
- AST 全部 walk して全 identifier みる
- シンボルに対して service.getRenameInfo() の canEdit をみる
- getEditsForRefactor() で text range をとる
- ts.transform で該当ノードを置換して document registry を更新

https://github.com/YousefED/typescript-json-schema
