# 删除文生图面具  
app\masks\cn.ts delete：
  以文搜图
# 增加模型名排序
app\utils\model.ts add：
```
/**
 * Generate full model table.
 */
export function collectModels(
  models: readonly LLMModel[],
  customModels: string,
) {
  const modelTable = collectModelTable(models, customModels);
  // const allModels = Object.values(modelTable);
  const allModels = Object.values(modelTable).sort((a, b) => a.displayName.localeCompare(b.displayName));

  return allModels;
}

export function collectModelsWithDefaultModel(
  models: readonly LLMModel[],
  customModels: string,
  defaultModel: string,
) {
  const modelTable = collectModelTableWithDefaultModel(
    models,
    customModels,
    defaultModel,
  );
  // const allModels = Object.values(modelTable);
  const allModels = Object.values(modelTable).sort((a, b) => a.displayName.localeCompare(b.displayName));
  return allModels;
}
```
# claude googe模型砖openai接口
startsWith.*claude modelName.startsWith("claude111") &&
startsWith.*gemini 
# 回退版本
$ hart
$ git push -f -u next main

# 合并代码过程
1 github中同步main分支
2 ide中同步main分支
3 ide中选择dev分支，合并main分支
4 提交dev分支到github，vercel自动编译成功后验证dev分支正确性。
5 ide中选择g4分支，合并dev分支，vercel自动编译后，完成升级。