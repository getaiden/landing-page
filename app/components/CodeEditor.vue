<template>
  <div class="terminal-container">
    <!-- Terminal header -->
    <div class="terminal-header">
      <div class="terminal-controls">
        <div class="control close"></div>
        <div class="control minimize"></div>
        <div class="control maximize"></div>
      </div>
      <div class="terminal-title">Python Console</div>
    </div>
    
    <!-- Terminal content -->
    <div class="terminal-content">
      <div class="line-numbers">
        <div v-for="n in 7" :key="n" class="line-number">{{ n }}</div>
      </div>
      <div class="code-area">
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span>
          <span class="keyword">from</span>
          <span class="normal"> aiden </span>
          <span class="normal">import </span>
          <span class="class-name">Transformation</span>
        </div>
        <div class="code-line">&nbsp;</div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span>
          <span class="normal">tr </span>
          <span class="operator">= </span>
          <span class="class-name">Transformation</span>
          <span class="normal">(</span>
        </div>
        <div class="code-line indent">
          <span class="string">"clean emails columns keep only valide ones"</span>
          <span class="normal">,</span>
        </div>
        <div class="code-line indent">
          <span class="keyword">input_schema</span>
          <span class="normal"> = </span>
          <span class="normal">{ </span>
          <span class="string">"email"</span>
          <span class="normal">: </span>
          <span class="builtin">str</span>
          <span class="normal"> }</span>
          <span class="normal">,</span>
        </div>
        <div class="code-line indent">
          <span class="keyword">output_schema</span>
          <span class="normal"> = </span>
          <span class="normal">{ </span>
          <span class="string">"email"</span>
          <span class="normal">: </span>
          <span class="builtin">str</span>
          <span class="normal"> }</span>
        </div>
        <div class="code-line">
          <span class="normal">)</span>
        </div>
        <div class="code-line">
          <span class="prompt">&gt;&gt;&gt;</span>
          <span class="normal">tr.</span>
          <span class="function">build</span>
          <span class="normal">()</span>
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
