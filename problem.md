1. 当使用 position： sticky 时候，当外面的box实用了 overflow： auto
   就会将 外面使用的作为 html一样 作为标准， 以他为相对位置
   <div style={{overflow: 'auto', padding: '20px;}}><div style={{ position: 'sticky', top: '0px'}}></div></div>
   里面的div往上移动时候，是以外面的div边框位置为准
2. 当react下来 props 里面有 onChange 传下来， 外面的div也含有props，就会出现问题，所以不能随便 ...props
  const { onChange } = this.props;
  <div {...props}> <input onChange={onChange}></input></div>
  像上面这样，在外面的props也有onChange，就会也会触发这个onChange，里面的div也会有这样的， 这样导致往外传的值也不确定， 也会出现问题的。
