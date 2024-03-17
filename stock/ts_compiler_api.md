export const ScrumMemberRole = {
ProductOwner: 'product_owner',
ScrumMaster: 'scrum_master',
Developer: 'developer',
} as const

export type ScrumMemberRoleType = (typeof ScrumMemberRole)[keyof typeof ScrumMemberRole]

[ TypeScript Compiler API の基本的な使い方、コード例と作ってみたもの ](https://katashin.info/2018/02/24/221)

[ttypescript](https://github.com/cevek/ttypescript#program)
Currently TypeScript doesn't support custom transformers in the tsconfig.json, but supports it programmatically.

And there is no way to compile your files using custom transformers using tsc command.

TTypescript (Transformer TypeScript) solves this problem by patching on the fly the compile module to use transformers from tsconfig.json.

Instead of tsc and tsserver, use ttsc and ttsserver wrappers. This wrappers try to use locally installed typescript first.

No version lock-ins - typescript used as peer dependency.

[ TypeScript Compiler API を使って型を中心に実装を自動生成する ](https://blog.nnn.dev/entry/2020/12/11/021008)

[ TypeScript Compiler API Factory Code Generator Generator ](https://github.com/dsherret/ts-factory-code-generator-generator)

[ TypeScript の compiler API をいじる ](https://akito0107.hatenablog.com/entry/2018/12/23/020323)

[ VSCode で TypeScript の交差型のプロパティを省略せずに見れるようにする](https://tech.mobilefactory.jp/entry/2021/12/02/000000)

TransoformerFactory について

[TypeScript 型レベルプログラミングの細かいテクニック](https://zenn.dev/suin/scraps/8828d6c915298c)

[TypeScript Compiler API で型を自動生成する仕組みを TDD で実装する](https://zenn.dev/panda_program/articles/typescript-compiler-api)

[Using-the-Compiler-API.md](https://github.com/microsoft/TypeScript-wiki/blob/main/Using-the-Compiler-API.md)

[TypeScript の型情報を展開して見やすくする VSCode 拡張機能を作った](https://zenn.dev/kimuson/articles/ts_type_expand)

[]()
[]()
[]()
[]()
[]()
[]()
[]()
[]()
[]()
[]()
[]()
[]()
[]()
[]()
[]()
