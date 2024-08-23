# Google Accounts



{% embed url="https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=DDS.drawio#R%3Cmxfile%20compressed%3D%22true%22%20locked%3D%22true%22%3E%3Cdiagram%20id%3D%22u8kCUlg2MoLbLQTSIHxo%22%20name%3D%22Page-1%22%3E7Vpdk9o2FP01zLQPu2PL34%2FAkiad3U5nSdM2LxmtrTXK2hYjiwXy63PlD8AIsJMaFzP7hH0sy9Y5R1e6Fw%2BMcbz6jeP57IEFJBogLVgNjLsBQkg3EPxIZJ0juq6bORJyGuSYtgWm9BspGpboggYkLbAcEoxFgs6roM%2BShPiigmHO2bLa7JlFQQWY45BUXkMCUx9HRGn2Nw3ELEdda6f1e0LDWflkXSuuxLhsXADpDAdsuQMZk4Ex5oyJ%2FChejUkk2avy8u7I1c2LcZKIJjeMvtx%2Fdkc3%2BvL3r9HHcPkXfxnHN0UvrzhaFAO%2BwwIDMo4ITmgSDmSvNo7nA2MExx85TtJnxmF0lCUA%2FDK6v%2F%2B1GKBYl6wtZ1SQ6Rz78nwJ1oC7U8HZy4ZEGP7olXBBgephRMMEMMGydi9E%2BLKJDif%2Bgr%2BSd1QI%2BSo59JWGYfYctOl0zCLGAQnIM15EInvVbFjwALI6ype%2BUQH8S1hMBF9Dk9K8hW7r8rQw7nJrA91Bdg7OdjxgaAWIC%2B%2BFm7638sBBodAPqIWOqfUJRzQoJPkpKS6FdNOqkG7Ytko6Mg9wbp6JckOhfLRIaULSFNB7FlJf%2FuI14UcnA5%2Bx%2BGmRHuT9oDoXooVuulU1kOEpaoBEqhobsHU5zEMzgAAyFTgJMA%2Fot2uYBkj3qvPA1NR5YB%2BKPeeaB5ZC%2FB84vj7iTcOqJ94xOiTeVoh%2FoGmar8yfMhBp70GCKIN6Tb6jGw3I79L1jkL%2BeJEKFoPZnyLJ%2FGTlR7AeZFuhMQeyOcU9V8HzzFoVkIk6VME9tu0ZhiEn4TXEHR15qN77htMh657KOoG0iKczOgf8ASeQ%2B8RyfLAIrFNBYrkDunuY%2Fmw6cCla2JZbkcJxVP%2B7XSpR5sLqBJisBMf%2BNfhfs1Ad6TrqlHQ1NX7ESwAk9U84JQrjvd3nI9eucI8OhB7TU7nfgO2Tr2a6ww83jwQH60KBbOfJ%2BBWp4Hh7Kti6KkO5SlRkKMH2ZVCz3%2BEHGftlnU8mwLuloUcyZ1zkG9NJEkKO3POYhLRyvT21E%2Bq0GqGr%2Ba9CcsZYUHCVCszFUNZBAUgYaGKMSBKUyFPE%2FBcJraj4p7hFHv8Lx9qtlZ0m8OLymlae7FzkbJEE2cO0doUjQVmWPSYbjJktuE9OsFVEJ6AgJKJ2fVV9wEkEe8vX6osc0jS7FTjF650Gc0YTkSqSb%2Fr%2FDy5Qk%2FFWXaDdet4PGOHifVDun%2BqNcCQgXKwR1OJAy0aAbHtrhFMuQMbl20BvaAPjvC4oev5TAjvrv2nv%2FeHg6nueybts10FqheOcC0qvw4jRNIqgnkURtb7y5oGaxKTeBGcOIq2bQC33tLuUVEzgoooLbm131wiXv7NsGgrOHAkariSmtfdlwP4NexXfvfbnWXmQWtRqexO7u3fReh12mkYd83%2Fx2%2F4fBpbTgX3U8tzbonX6T%2FNa91j9WrJKxd8sUG8Bq6EF7J5ZQC1Qvlng9IcEtRZwemaBbkuivbaA09ACbs8scOZ66DVZwG1ogYtJX%2BF0%2B4103nz7qbkx%2BQ4%3D%3C%2Fdiagram%3E%3C%2Fmxfile%3E" %}

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### &#x20;<a href="#headingtext" id="headingtext"></a>

### &#x20;<a href="#headingtext" id="headingtext"></a>

### &#x20;<a href="#headingtext" id="headingtext"></a>

### import React, { useState } from 'react' import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card" import { Button } from "@/components/ui/button" import { Input } from "@/components/ui/input" import { Label } from "@/components/ui/label" import { Slider } from "@/components/ui/slider" import { Switch } from "@/components/ui/switch" import { Select, SelectContent, SelectItem, SelectTrigger, SelectValue } from "@/components/ui/select" import { ArrowLeft, Save, Database, RefreshCw } from 'lucide-react' <a href="#headingtext" id="headingtext"></a>

export default function AISettings() { const \[model, setModel] = useState("gpt-4") const \[temperature, setTemperature] = useState(0.7) const \[maxTokens, setMaxTokens] = useState(2048) const \[topP, setTopP] = useState(1) const \[frequencyPenalty, setFrequencyPenalty] = useState(0) const \[presencePenalty, setPresencePenalty] = useState(0) const \[dailyLimit, setDailyLimit] = useState(10000) const \[enableContentFiltering, setEnableContentFiltering] = useState(true) const \[lastSyncTime, setLastSyncTime] = useState("2023-08-25 14:30:00") const \[isSyncing, setIsSyncing] = useState(false)

const handleSave = () => { // Here you would typically send the settings to your backend console.log("Saving settings:", { model, temperature, maxTokens, topP, frequencyPenalty, presencePenalty, dailyLimit, enableContentFiltering }) // Show a success message to the user alert("Settings saved successfully!") }

const handleSync = () => { setIsSyncing(true) // Simulating a sync process setTimeout(() => { setIsSyncing(false) setLastSyncTime(new Date().toLocaleString()) alert("Database synchronized successfully!") }, 2000) }

return (

## AI Model Settings

{% code title="Ai Model Setting Page" overflow="wrap" lineNumbers="true" fullWidth="true" %}
```tsx
import React, { useState } from 'react'
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card"
import { Button } from "@/components/ui/button"
import { Input } from "@/components/ui/input"
import { Label } from "@/components/ui/label"
import { Slider } from "@/components/ui/slider"
import { Switch } from "@/components/ui/switch"
import { Select, SelectContent, SelectItem, SelectTrigger, SelectValue } from "@/components/ui/select"
import { ArrowLeft, Save, Database, RefreshCw } from 'lucide-react'

export default function AISettings() {
  const [model, setModel] = useState("gpt-4")
  const [temperature, setTemperature] = useState(0.7)
  const [maxTokens, setMaxTokens] = useState(2048)
  const [topP, setTopP] = useState(1)
  const [frequencyPenalty, setFrequencyPenalty] = useState(0)
  const [presencePenalty, setPresencePenalty] = useState(0)
  const [dailyLimit, setDailyLimit] = useState(10000)
  const [enableContentFiltering, setEnableContentFiltering] = useState(true)
  const [lastSyncTime, setLastSyncTime] = useState("2023-08-25 14:30:00")
  const [isSyncing, setIsSyncing] = useState(false)

  const handleSave = () => {
    // Here you would typically send the settings to your backend
    console.log("Saving settings:", {
      model,
      temperature,
      maxTokens,
      topP,
      frequencyPenalty,
      presencePenalty,
      dailyLimit,
      enableContentFiltering
    })
    // Show a success message to the user
    alert("Settings saved successfully!")
  }

  const handleSync = () => {
    setIsSyncing(true)
    // Simulating a sync process
    setTimeout(() => {
      setIsSyncing(false)
      setLastSyncTime(new Date().toLocaleString())
      alert("Database synchronized successfully!")
    }, 2000)
  }

  return (
    <div className="p-8 bg-gray-900 text-gray-100 min-h-screen">
      <div className="flex items-center mb-6">
        <Button variant="outline" size="icon" className="mr-4">
          <ArrowLeft className="h-4 w-4" />
        </Button>
        <h1 className="text-2xl font-bold">AI Model Settings</h1>
      </div>

      <Card className="bg-gray-800 border-gray-700 mb-6">
        <CardHeader>
          <CardTitle className="text-xl text-gray-100">Model Configuration</CardTitle>
        </CardHeader>
        <CardContent className="space-y-4">
          <div className="space-y-2">
            <Label htmlFor="model" className="text-gray-200">AI Model</Label>
            <Select value={model} onValueChange={setModel}>
              <SelectTrigger id="model" className="bg-gray-700 border-gray-600 text-gray-100">
                <SelectValue placeholder="Select a model" />
              </SelectTrigger>
              <SelectContent className="bg-gray-700 border-gray-600">
                <SelectItem value="gpt-4" className="text-gray-100">GPT-4</SelectItem>
                <SelectItem value="gpt-3.5-turbo" className="text-gray-100">GPT-3.5 Turbo</SelectItem>
                <SelectItem value="davinci" className="text-gray-100">Davinci</SelectItem>
              </SelectContent>
            </Select>
          </div>

          <div className="space-y-2">
            <Label htmlFor="temperature" className="text-gray-200">Temperature: {temperature}</Label>
            <Slider
              id="temperature"
              min={0}
              max={1}
              step={0.1}
              value={[temperature]}
              onValueChange={([value]) => setTemperature(value)}
              className="text-emerald-500"
            />
          </div>

          <div className="space-y-2">
            <Label htmlFor="maxTokens" className="text-gray-200">Max Tokens: {maxTokens}</Label>
            <Slider
              id="maxTokens"
              min={1}
              max={4096}
              step={1}
              value={[maxTokens]}
              onValueChange={([value]) => setMaxTokens(value)}
              className="text-emerald-500"
            />
          </div>

          <div className="space-y-2">
            <Label htmlFor="topP" className="text-gray-200">Top P: {topP}</Label>
            <Slider
              id="topP"
              min={0}
              max={1}
              step={0.1}
              value={[topP]}
              onValueChange={([value]) => setTopP(value)}
              className="text-emerald-500"
            />
          </div>

          <div className="space-y-2">
            <Label htmlFor="frequencyPenalty" className="text-gray-200">Frequency Penalty: {frequencyPenalty}</Label>
            <Slider
              id="frequencyPenalty"
              min={-2}
              max={2}
              step={0.1}
              value={[frequencyPenalty]}
              onValueChange={([value]) => setFrequencyPenalty(value)}
              className="text-emerald-500"
            />
          </div>

          <div className="space-y-2">
            <Label htmlFor="presencePenalty" className="text-gray-200">Presence Penalty: {presencePenalty}</Label>
            <Slider
              id="presencePenalty"
              min={-2}
              max={2}
              step={0.1}
              value={[presencePenalty]}
              onValueChange={([value]) => setPresencePenalty(value)}
              className="text-emerald-500"
            />
          </div>
        </CardContent>
      </Card>

      <Card className="bg-gray-800 border-gray-700 mb-6">
        <CardHeader>
          <CardTitle className="text-xl text-gray-100">Usage Limits</CardTitle>
        </CardHeader>
        <CardContent className="space-y-4">
          <div className="space-y-2">
            <Label htmlFor="dailyLimit" className="text-gray-200">Daily Token Limit</Label>
            <Input
              id="dailyLimit"
              type="number"
              value={dailyLimit}
              onChange={(e) => setDailyLimit(parseInt(e.target.value))}
              className="bg-gray-700 border-gray-600 text-gray-100"
            />
          </div>
        </CardContent>
      </Card>

      <Card className="bg-gray-800 border-gray-700 mb-6">
        <CardHeader>
          <CardTitle className="text-xl text-gray-100">Content Filtering</CardTitle>
        </CardHeader>
        <CardContent>
          <div className="flex items-center space-x-2">
            <Switch
              id="content-filtering"
              checked={enableContentFiltering}
              onCheckedChange={setEnableContentFiltering}
            />
            <Label htmlFor="content-filtering" className="text-gray-200">Enable content filtering</Label>
          </div>
        </CardContent>
      </Card>

      <Card className="bg-gray-800 border-gray-700 mb-6">
        <CardHeader>
          <CardTitle className="text-xl text-gray-100">Database Synchronization</CardTitle>
        </CardHeader>
        <CardContent className="space-y-4">
          <div className="flex items-center justify-between">
            <div>
              <Label className="text-gray-200">Last Sync Time</Label>
              <p className="text-gray-400">{lastSyncTime}</p>
            </div>
            <Button 
              onClick={handleSync} 
              disabled={isSyncing}
              className="bg-blue-600 hover:bg-blue-700 text-white"
            >
              {isSyncing ? (
                <RefreshCw className="h-4 w-4 mr-2 animate-spin" />
              ) : (
                <Database className="h-4 w-4 mr-2" />
              )}
              {isSyncing ? 'Syncing...' : 'Sync Database'}
            </Button>
          </div>
          <p className="text-sm text-gray-400">
            Synchronize the AI model with the latest data from your dealership database. 
            This process may take a few minutes.
          </p>
        </CardContent>
      </Card>

      <div className="flex justify-end">
        <Button onClick={handleSave} className="bg-emerald-600 hover:bg-emerald-700 text-white">
          <Save className="h-4 w-4 mr-2" />
          Save Settings
        </Button>
      </div>
    </div>
  )
}
```
{% endcode %}

) }Something went wrong

Sorry, something went wrong there. Try again.
