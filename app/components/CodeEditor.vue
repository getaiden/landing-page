<template>
  <div class="terminal-container">
    <!-- Terminal header -->
    <div class="terminal-header">
      <div class="terminal-controls">
        <div class="control close" />
        <div class="control minimize" />
        <div class="control maximize" />
      </div>
      <div class="terminal-title">
        Python Console
      </div>
    </div>

    <!-- Terminal content -->
    <div class="terminal-content">
      <div class="line-numbers">
        <div v-for="n in 37" :key="n" class="line-number">
          {{ n }}
        </div>
      </div>
      <div class="code-area">
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span> <span class="keyword">from</span><span class="normal"> aiden </span><span class="keyword">import</span> <span class="class-name">Transformation</span>
        </div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span> <span class="keyword">from</span><span class="normal"> aiden.common.dataset </span><span class="keyword">import</span> <span class="class-name">Dataset</span>
        </div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span> <span class="keyword">from</span><span class="normal"> aiden.common.environment </span><span class="keyword">import</span> <span class="class-name">Environment</span>
        </div>
        <div class="code-line">
          <span class="normal">&nbsp;</span>
        </div>
        <div class="code-line">
          <span class="normal" style="color: #6272A4;"># Define input and output datasets</span>
        </div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span> <span class="normal">in_dev_dataset </span><span class="operator">=</span> <span class="class-name">Dataset</span><span class="normal">(</span>
        </div>
        <div class="code-line indent">
          <span class="normal">path</span><span class="operator">=</span><span class="string">"./tests/input_data/emails.csv"</span><span class="normal">,</span>
        </div>
        <div class="code-line indent">
          <span class="normal">format</span><span class="operator">=</span><span class="string">"csv"</span><span class="normal">,</span>
        </div>
        <div class="code-line indent">
          <span class="normal">schema</span><span class="operator">=</span><span class="normal">{</span><span class="string">"email"</span><span class="operator">:</span> <span class="builtin">str</span><span class="normal">},</span>
        </div>
        <div class="code-line">
          <span class="normal">)</span>
        </div>
        <div class="code-line">
          <span class="normal">&nbsp;</span>
        </div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span> <span class="normal">out_dev_dataset </span><span class="operator">=</span> <span class="class-name">Dataset</span><span class="normal">(</span>
        </div>
        <div class="code-line indent">
          <span class="normal">path</span><span class="operator">=</span><span class="string">"./tests/output_data/clean_emails.csv"</span><span class="normal">,</span>
        </div>
        <div class="code-line indent">
          <span class="normal">format</span><span class="operator">=</span><span class="string">"csv"</span><span class="normal">,</span>
        </div>
        <div class="code-line indent">
          <span class="normal">schema</span><span class="operator">=</span><span class="normal">{</span><span class="string">"email"</span><span class="operator">:</span> <span class="builtin">str</span><span class="normal">},</span>
        </div>
        <div class="code-line">
          <span class="normal">)</span>
        </div>
        <div class="code-line">
          <span class="normal">&nbsp;</span>
        </div>
        <div class="code-line">
          <span class="normal" style="color: #6272A4;"># Create environment object with custom workdir</span>
        </div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span> <span class="normal">env </span><span class="operator">=</span> <span class="class-name">Environment</span><span class="normal">(</span>
        </div>
        <div class="code-line indent">
          <span class="normal">type</span><span class="operator">=</span><span class="string">"dagster"</span><span class="normal">,</span>
        </div>
        <div class="code-line indent">
          <span class="normal">workdir</span><span class="operator">=</span><span class="string">"./tests/workdir/"</span><span class="normal">,</span>
        </div>
        <div class="code-line">
          <span class="normal">)</span>
        </div>
        <div class="code-line">
          <span class="normal">&nbsp;</span>
        </div>
        <div class="code-line">
          <span class="normal" style="color: #6272A4;"># Define transformation with natural language intent</span>
        </div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span> <span class="normal">tr </span><span class="operator">=</span> <span class="class-name">Transformation</span><span class="normal">(</span>
        </div>
        <div class="code-line indent">
          <span class="normal">intent</span><span class="operator">=</span><span class="string">"clean emails column and keep only valid ones."</span><span class="normal">,</span>
        </div>
        <div class="code-line indent">
          <span class="normal">environment</span><span class="operator">=</span><span class="normal">env,</span>
        </div>
        <div class="code-line">
          <span class="normal">)</span>
        </div>
        <div class="code-line">
          <span class="normal">&nbsp;</span>
        </div>
        <div class="code-line">
          <span class="normal" style="color: #6272A4;"># Build the transformation with specified datasets and providers</span>
        </div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span> <span class="normal">tr.</span><span class="function">build</span><span class="normal">(</span>
        </div>
        <div class="code-line indent">
          <span class="normal">input_datasets</span><span class="operator">=</span><span class="normal">[in_dev_dataset],</span>
        </div>
        <div class="code-line indent">
          <span class="normal">output_dataset</span><span class="operator">=</span><span class="normal">out_dev_dataset,</span>
        </div>
        <div class="code-line">
          <span class="normal">)</span>
        </div>
        <div class="code-line">
          <span class="normal">&nbsp;</span>
        </div>
        <div class="code-line">
          <span class="normal" style="color: #6272A4;"># Deploy the transformation</span>
        </div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span> <span class="normal">tr.</span><span class="function">save</span><span class="normal">(</span><span class="string">"./path/to/artifacts/email_transformation.py"</span><span class="normal">)</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
// No longer needed as we're using HTML for syntax highlighting
// const pythonCode = `...`
</script>

<style scoped>
.terminal-container {
  width: 100%;
  max-width: 700px;
  margin: 0 auto;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15);
  font-family: 'Menlo', 'Monaco', 'Courier New', monospace;
}

.terminal-header {
  background-color: #1E1F29;
  padding: 8px 12px;
  display: flex;
  align-items: center;
  position: relative;
}

.terminal-controls {
  display: flex;
  gap: 8px;
}

.control {
  width: 14px;
  height: 14px;
  border-radius: 50%;
}

.close {
  background-color: #FF5F56;
}

.minimize {
  background-color: #FFBD2E;
}

.maximize {
  background-color: #27C93F;
}

.terminal-title {
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  color: white;
  font-size: 14px;
  font-family: Arial, sans-serif;
}

.terminal-content {
  background-color: #282A36;
  color: #F8F8F2;
  padding: 16px;
  display: flex;
}

.line-numbers {
  color: #6272A4;
  text-align: right;
  padding-right: 12px;
  user-select: none;
  font-size: 16px;
  line-height: 1.5;
}

.line-number {
  padding: 0 5px;
}

.code-area {
  flex: 1;
  font-size: 16px;
  line-height: 1.5;
}

.code-line {
  white-space: pre;
  padding: 0 5px;
}

.indent {
  padding-left: 40px;
}

/* Syntax highlighting */
.normal {
  color: #F8F8F2;
}

.prompt {
  color: #FF79C6;
  margin-right: 10px;
}

.keyword {
  color: #8BE9FD;
}

.operator {
  color: #FF79C6;
}

.string {
  color: #F1FA8C;
}

.function {
  color: #50FA7B;
}

.class-name {
  color: #50FA7B;
}

.builtin {
  color: #8BE9FD;
}
</style>
