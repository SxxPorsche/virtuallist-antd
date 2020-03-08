# virtuallist-antd

> 

[![NPM](https://img.shields.io/npm/v/virtuallist-antd.svg)](https://www.npmjs.com/package/virtuallist-antd) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

> 仓库: https://github.com/crawler-django/virtuallist-antd    

> 版本更新记录: https://github.com/crawler-django/virtuallist-antd/blob/master/update.md

virtualList for antd-table, 实现antd-table的虚拟列表, antd-table无限滚动, infinite scrolling for antd-table

* 已经支持4.0的antd-table.(4.x ---- v0.3.0后,  3.x ---- v0.2.8.)
* 你可以像平常一样在columns里使用fixed
* 支持进行条件搜索 变更数据.
* 目前用了节流 - 60ms 在滚动的时候刷新窗口
* 支持分页
* 只支持纵向虚拟列表.
* 此组件会计算每行的高度, 并且固定每行的高度, 以第一行的高度为准. 组件有自带的css, 会使每行的td不会换行.

## example
* [简单的例子](https://codesandbox.io/s/festive-worker-wc5wp)
* [简单的分页例子](https://codesandbox.io/s/gracious-resonance-tmw44)

## Install

```bash
npm install --save virtuallist-antd
```

## Usage

```tsx
import * as React from 'react'
import ReactDom from 'react-dom'

import { VList } from 'virtuallist-antd'
import { Table } from 'antd'

function Example(): JSX.Element {
	const dataSource = [...]
	const columns = [...]
	const rowkey = 'xxx'
	return (
		<Table 
			dataSource={dataSource}
			columns={columns}
			rowKey={rowKey}
			scroll={{
				y: 1000 // 滚动的高度, 可以是受控属性。
			}}
			// 使用VList 即可有虚拟列表的效果
			components={VList({
				height: 1000 // 此值和scrollY值相同. 必传. (required). 
			})}
		/>
	)
}

ReactDom.render(<Example />, dom)

```

## License

MIT © [crawler-django](https://github.com/crawler-django)
