<script setup>
import { onMounted } from 'vue';
import { render_markdown } from "rust"

const title = ref("Markdown to html")
const md_input = ref("# Heading\n\n- Red\n- Green\n- Blue\n\n[example.com](https://example.com/)\n\n![](/milky-way.jpg)")
const html_output = ref("")
const display_preview = ref(true)
const md_textarea = ref(null)

function render_md() {
    html_output.value = render_markdown(md_input.value)
}

onMounted(() => {
    render_md()
    md_textarea.value.focus()
})
</script>

<template>
    <Head>
        <Title>{{ title }}</Title>
    </Head>
    <div class="container">
        <div class="head">
            <div class="head_title_container">
                <h1>{{ title }}</h1>
                <div class="head_link_container">
                    <a href="https://github.com/raphlinus/pulldown-cmark">pulldown-cmark</a>
                    <div> + Nuxt</div>
                    <a href="https://github.com/hitorigoya/markdown-html">
                        <svg width="17" height="16" viewBox="0 0 17 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M5.48875 12.8832C5.48875 12.9493 5.41265 13.0023 5.31671 13.0023C5.20753 13.0122 5.13143 12.9593 5.13143 12.8832C5.13143 12.817 5.20753 12.7641 5.30347 12.7641C5.40273 12.7541 5.48875 12.8071 5.48875 12.8832ZM4.45982 12.7343C4.43666 12.8005 4.50283 12.8766 4.60208 12.8964C4.6881 12.9295 4.78735 12.8964 4.8072 12.8302C4.82706 12.7641 4.76419 12.688 4.66494 12.6582C4.57892 12.635 4.48297 12.6681 4.45982 12.7343ZM5.92216 12.6781C5.82621 12.7012 5.76004 12.7641 5.76997 12.8402C5.77989 12.9063 5.86591 12.9493 5.96517 12.9262C6.06111 12.903 6.12728 12.8402 6.11736 12.774C6.10743 12.7111 6.0181 12.6681 5.92216 12.6781ZM8.09913 0C3.51029 0 0 3.48382 0 8.07266C0 11.7418 2.30931 14.8815 5.60785 15.9865C6.03134 16.0626 6.18022 15.8012 6.18022 15.5862C6.18022 15.3811 6.17029 14.2496 6.17029 13.5548C6.17029 13.5548 3.85437 14.0511 3.36802 12.5689C3.36802 12.5689 2.99086 11.6061 2.44827 11.358C2.44827 11.358 1.69063 10.8385 2.5012 10.8485C2.5012 10.8485 3.32501 10.9146 3.77827 11.7021C4.50283 12.9791 5.71703 12.6119 6.19014 12.3935C6.26624 11.8642 6.48129 11.4969 6.7195 11.2786C4.87007 11.0734 3.00409 10.8055 3.00409 7.62271C3.00409 6.71288 3.25553 6.25631 3.78489 5.67402C3.69887 5.45897 3.41765 4.5723 3.87091 3.42757C4.56238 3.21252 6.15375 4.32086 6.15375 4.32086C6.81544 4.13559 7.52677 4.03964 8.23147 4.03964C8.93617 4.03964 9.64749 4.13559 10.3092 4.32086C10.3092 4.32086 11.9006 3.20921 12.592 3.42757C13.0453 4.57561 12.7641 5.45897 12.6781 5.67402C13.2074 6.25962 13.5316 6.71619 13.5316 7.62271C13.5316 10.8154 11.5829 11.0701 9.73351 11.2786C10.0379 11.5399 10.296 12.0362 10.296 12.8137C10.296 13.9287 10.286 15.3083 10.286 15.5796C10.286 15.7946 10.4382 16.056 10.8584 15.9799C14.1669 14.8815 16.41 11.7418 16.41 8.07266C16.41 3.48382 12.688 0 8.09913 0ZM3.21583 11.4109C3.17282 11.444 3.18275 11.5201 3.23899 11.5829C3.29193 11.6359 3.36802 11.659 3.41103 11.616C3.45404 11.5829 3.44412 11.5069 3.38787 11.444C3.33494 11.3911 3.25884 11.3679 3.21583 11.4109ZM2.85852 11.1429C2.83536 11.1859 2.86844 11.2389 2.93461 11.272C2.98755 11.305 3.05372 11.2951 3.07688 11.2488C3.10003 11.2058 3.06695 11.1528 3.00078 11.1198C2.93461 11.0999 2.88168 11.1098 2.85852 11.1429ZM3.93046 12.3207C3.87752 12.3637 3.89738 12.463 3.97347 12.5259C4.04957 12.602 4.14551 12.6119 4.18852 12.5589C4.23153 12.5159 4.21168 12.4167 4.14551 12.3538C4.07272 12.2777 3.97347 12.2678 3.93046 12.3207ZM3.5533 11.8344C3.50036 11.8675 3.50036 11.9535 3.5533 12.0296C3.60623 12.1057 3.69556 12.1388 3.73857 12.1057C3.7915 12.0627 3.7915 11.9767 3.73857 11.9006C3.69225 11.8245 3.60623 11.7914 3.5533 11.8344Z"
                                fill="currentColor" />
                        </svg>
                    </a>
                </div>
            </div>
            <div class="head_inline_container">
                <div class="head_inline_title">Syntax</div>
                <div class="head_inline_title">Markdown</div>
                <div class="toggle_container">
                    <button @click="display_preview = true" :class="{ active: display_preview }">Preview</button>
                    <button @click="display_preview = false" :class="{ active: !display_preview }">HTML</button>
                </div>
            </div>
        </div>
        <div class="main">
            <div class="md_syntax_container">
                <!-- Heading -->
                <table>
                    <tr>
                        <th>Heading</th>
                    </tr>
                    <tr>
                        <td><code># Heading 1</code></td>
                    </tr>
                    <tr>
                        <td><code>## Heading 2</code></td>
                    </tr>
                    <tr>
                        <td><code>### Heading 3</code></td>
                    </tr>
                </table>
                <!-- List -->
                <table>
                    <tr>
                        <th>List</th>
                    </tr>
                    <tr>
                        <td>
                            <code>- Red<br>- Green<br>- Blue</code>
                        </td>
                    </tr>
                    <tr>
                        <td>
                            <code>1. Red<br>2. Green<br>3. Blue</code>
                        </td>
                    </tr>
                </table>
                <!-- Link -->
                <table>
                    <tr>
                        <th>Link</th>
                    </tr>
                    <tr>
                        <td><code>[example.com](https://example.com/)</code></td>
                    </tr>
                </table>
                <!-- Image -->
                <table>
                    <tr>
                        <th>Image</th>
                    </tr>
                    <tr>
                        <td><code>![](/milky-way.jpg)</code></td>
                    </tr>
                </table>
                <!-- Linking Image -->
                <table>
                    <tr>
                        <th>Linking Image</th>
                    </tr>
                    <tr>
                        <td><code>[![](/milky-way.jpg)](/milky-way.jpg)</code></td>
                    </tr>
                </table>
                <!-- Code -->
                <table>
                    <tr>
                        <th>Code</th>
                    </tr>
                    <tr>
                        <td><code>`console.log("Hello World!")`</code></td>
                    </tr>
                    <tr>
                        <td><code>```js<br>console.log("Hello World!")<br>```</code></td>
                    </tr>
                </table>
            </div>
            <div class="md_input_container">
                <textarea v-model="md_input" @keyup="render_md" ref="md_textarea"></textarea>
            </div>
            <div class="output_container">
                <div v-show="display_preview" class="preview" v-html="html_output"></div>
                <textarea v-show="!display_preview" v-model="html_output"></textarea>
            </div>
        </div>
    </div>
</template>

<style scoped>
.head {
    height: 80px;
    display: grid;
    grid-template-rows: 1fr 1fr;
    line-height: 1;
    padding-left: 48px;
    padding-right: 48px;
}

.head a {
    color: var(--color-text-primary);
    text-decoration: underline;
}

.head_title_container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 8px;
}

h1 {
    font-size: 18px;
    margin: 0;
}

.head_link_container {
    display: flex;
    gap: 8px;
}

.head_inline_container {
    display: grid;
    grid-template-columns: 0.5fr 1fr 1fr;
    align-items: center;
    gap: 16px;
}

.head_inline_title {
    color: var(--color-link);
}

.main {
    display: grid;
    grid-template-columns: 0.5fr 1fr 1fr;
    gap: 16px;
    padding-left: 48px;
    padding-right: 48px;
}

table {
    font-size: 14px;
    margin-bottom: 16px;
    width: 100%;
}

th {
    text-align: start;
}

textarea {
    color: var(--color-text-primary);
    background-color: var(--color-bg-primary);
    width: 100%;
    padding: 12px 16px;
}

.md_input_container {
    height: calc(100vh - 80px);
    top: 80px;
    overflow: auto;
    display: grid;
}

.output_container {
    height: calc(100vh - 80px);
    top: 80px;
    overflow: auto;
    display: grid;
}

button {
    border: none;
    padding: 0;
    margin: 0;
    margin-right: 24px;
    font-size: 16px;
    color: var(--color-text-primary);
    background-color: transparent;
}

button:hover {
    cursor: pointer;
}

.active {
    color: var(--color-link);
}
</style>