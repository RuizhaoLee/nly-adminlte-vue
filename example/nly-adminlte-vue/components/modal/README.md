# Modal

> 模态框是一种悬浮悬浮于主窗口的用来现实额外内容的对话框，允许自定义对话内容，几乎可以内嵌其他任何组件和元素。

``` html
<div>
    <nly-button variant="primary" v-nly-modal.no-close-on-esc.modal-1>点击弹出Modal</nly-button>

    <nly-modal id="modal-1" title="NlyAdminlteVue">
        <p class="my-4">Hello NlyAdminlteVue</p>
    </nly-modal>
</div>

<!-- 总览.name -->
<!-- nly-modal.vue -->
```

## 总览

在默认下， `nly-modal` 在底部有 取消 和 确定的按钮，用来进行确认操作和关闭操作。 可以通过 `nly-modal` 的专门prop来对这些按钮进行设置。同时也可以用对应的 `modal-ok` 和 `modal-cancel` 插槽来嵌入其他元素和组件来替换按钮。

`nly-modal` 在默认下是可以使用键盘上的 `ESC` 按键来关闭的，也可以通过点击 `nly-modal` 的罩层来关闭，还可以通过点击 `nly-modal` 右上角的 X 按钮来关闭。 这些关闭行为都是默认的。您可以通过设置 prop `no-close-on-esc` , `no-close-on-backdrop` , `hide-header-close` 来禁止对应的行为, 指令 `nly-modal` 无效。

可以设置 `modal-title` , `modal-header` , `modal-footer` 插槽来设置元素和组件嵌入 model的标题，头部和底部

`nly-modal` 懒加载模式不会渲染dom元素，只有在点击触发显示的时候才会渲染，您可以设置 `static` 来实现初始渲染

**注意**

使用 `modal-footer` 插槽时，默认的 确定 和 取消 按钮不会显示，需要您自己设置。如果您使用 `modal-header` 插槽，默认的页眉关闭按钮 X 也不会显示，也无法使用 `modal-title` 插槽。

## 切换 `nly-modal` 的隐藏和展示状态

您可以通过以下方法来关闭和显示模态框

### 使用 `v-nly-modal` 指令

`v-nly-modal` 可以快速控制 `nly-modal` 显示和隐藏

``` html
<div>
    <!-- 使用 modifiers -->
    <nly-button variant="primary" v-nly-modal.my-modal>点击显示</nly-button>

    <!-- 使用 value -->
    <nly-button variant="primary" v-nly-modal="'my-modal'">点击显示</nly-button>

    <nly-modal id="my-modal">Hello NlyAdminlteVue</nly-modal>
</div>

<!-- v-nly-modal 指令显示隐藏.name -->
<!-- v-nly-modal.vue -->
```

### 使用 `$bvModal`

如果是 `import "NlyAdminlteVue" ...` 或者注册为 插件的时候（`ModalPlugin`）