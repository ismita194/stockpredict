import React, { useState, useEffect, useRef } from 'react';
import { TrendingUp, TrendingDown, Send, Calendar, Zap, Info, Download } from 'lucide-react';

const Chart = window.Chart;

export default function StockPredictionDashboard() {
  const [selectedStock, setSelectedStock] = useState('AAPL');
  const [customStock, setCustomStock] = useState('');
  const [selectedModel, setSelectedModel] = useState('ensemble');
  const [predictionDays, setPredictionDays] = useState(30);
  const [predictions, setPredictions] = useState(null);
  const [loading, setLoading] = useState(false);
  const [chartData, setChartData] = useState([]);
  const chartRef = useRef(null);
  const chartInstance = useRef(null);

  // Popular stocks list
  const popularStocks = [
    { symbol: 'AAPL', name: 'Apple Inc.' },
    { symbol: 'MSFT', name: 'Microsoft Corp.' },
    { symbol: 'GOOGL', name: 'Alphabet Inc.' },
    { symbol: 'TSLA', name: 'Tesla Inc.' },
    { symbol: 'AMZN', name: 'Amazon.com Inc.' },
    { symbol: 'NVDA', name: 'NVIDIA Corp.' },
    { symbol: 'META', name: 'Meta Platforms' },
    { symbol: 'RELIANCE.NS', name: 'Reliance Industries' },
  ];

  const models = [
    { id: 'lr', name: 'Linear Regression', accuracy: 87, color: '#3B82F6' },
    { id: 'knn', name: 'KNN', accuracy: 89, color: '#8B5CF6' },
    { id: 'svr', name: 'SVR', accuracy: 90, color: '#F59E0B' },
    { id: 'rf', name: 'Random Forest', accuracy: 92, color: '#10B981' },
    { id: 'xgb', name: 'XGBoost', accuracy: 93, color: '#EF4444' },
    { id: 'lstm', name: 'LSTM', accuracy: 94, color: '#06B6D4' },
    { id: 'ensemble', name: 'Ensemble (Best)', accuracy: 95, color: '#2563EB' },
  ];

  // Generate mock chart data
  const generateChartData = () => {
    const data = [];
    const basePrice = 150 + Math.random() * 100;
    for (let i = 0; i < 60; i++) {
      data.push({
        date: new Date(Date.now() - (60 - i) * 24 * 60 * 60 * 1000).toLocaleDateString('en-US', { 
          month: 'short', 
          day: 'numeric' 
        }),
        actual: basePrice + Math.sin(i / 10) * 30 + Math.random() * 20 - 10,
        predicted: basePrice + Math.sin(i / 10) * 28 + Math.random() * 15,
      });
    }
    return data;
  };

  useEffect(() => {
    setChartData(generateChartData());
  }, [selectedStock]);

  // Handle prediction
  const handlePredict = async (e) => {
    e.preventDefault();
    
    if (!selectedStock) {
      alert('Please select a stock');
      return;
    }

    setLoading(true);

    // Simulate API call
    setTimeout(() => {
      const lastData = chartData[chartData.length - 1];
      const currentPrice = lastData?.actual || 150;
      const predictedPrice = currentPrice + (Math.random() - 0.5) * 30;
      const change = predictedPrice - currentPrice;
      const percentChange = ((change / currentPrice) * 100).toFixed(2);
      const confidence = (75 + Math.random() * 20).toFixed(1);

      setPredictions({
        stock: selectedStock,
        stockName: popularStocks.find(s => s.symbol === selectedStock)?.name || selectedStock,
        model: models.find(m => m.id === selectedModel)?.name,
        currentPrice: currentPrice.toFixed(2),
        predictedPrice: predictedPrice.toFixed(2),
        change: change.toFixed(2),
        percentChange,
        days: predictionDays,
        confidence,
        rmse: (5 + Math.random() * 8).toFixed(2),
        mae: (3 + Math.random() * 6).toFixed(2),
        r2: (0.85 + Math.random() * 0.12).toFixed(3),
        timestamp: new Date().toLocaleString(),
      });

      setLoading(false);
    }, 1500);
  };

  // Initialize chart
  useEffect(() => {
    if (!chartRef.current || !window.Chart || chartData.length === 0) return;

    const ctx = chartRef.current.getContext('2d');

    if (chartInstance.current) {
      chartInstance.current.destroy();
    }

    chartInstance.current = new window.Chart(ctx, {
      type: 'line',
      data: {
        labels: chartData.map(d => d.date),
        datasets: [
          {
            label: `${selectedStock} - Actual Price`,
            data: chartData.map(d => d.actual),
            borderColor: '#1F2937',
            backgroundColor: 'rgba(31, 41, 55, 0.05)',
            borderWidth: 2.5,
            fill: true,
            tension: 0.4,
            pointRadius: 0,
            pointHoverRadius: 8,
            pointBackgroundColor: '#1F2937',
          },
          {
            label: `${models.find(m => m.id === selectedModel)?.name} - Prediction`,
            data: chartData.map(d => d.predicted),
            borderColor: models.find(m => m.id === selectedModel)?.color,
            backgroundColor: 'transparent',
            borderWidth: 2.5,
            borderDash: [5, 5],
            fill: false,
            tension: 0.4,
            pointRadius: 0,
            pointHoverRadius: 8,
            pointBackgroundColor: models.find(m => m.id === selectedModel)?.color,
          },
        ],
      },
      options: {
        responsive: true,
        maintainAspectRatio: true,
        plugins: {
          legend: {
            display: true,
            position: 'top',
            labels: {
              usePointStyle: true,
              padding: 20,
              font: { size: 13, weight: '500' },
              color: '#6B7280',
            },
          },
          tooltip: {
            backgroundColor: 'rgba(255, 255, 255, 0.95)',
            titleColor: '#1F2937',
            bodyColor: '#1F2937',
            borderColor: '#E5E7EB',
            borderWidth: 1,
            padding: 12,
            displayColors: true,
          },
        },
        scales: {
          y: {
            beginAtZero: false,
            ticks: {
              color: '#9CA3AF',
              font: { size: 12 },
              callback: (value) => `$${value.toFixed(0)}`,
            },
            grid: {
              color: 'rgba(229, 231, 235, 0.5)',
              drawBorder: false,
            },
          },
          x: {
            ticks: {
              color: '#9CA3AF',
              font: { size: 12 },
              maxRotation: 0,
            },
            grid: {
              display: false,
              drawBorder: false,
            },
          },
        },
      },
    });

    return () => {
      if (chartInstance.current) {
        chartInstance.current.destroy();
      }
    };
  }, [selectedModel, chartData, models]);

  const exportPrediction = () => {
    if (!predictions) return;
    const csv = `Stock Prediction Report\n\nStock,${predictions.stock}\nName,${predictions.stockName}\nCurrent Price,${predictions.currentPrice}\nPredicted Price,${predictions.predictedPrice}\nChange,${predictions.change} (${predictions.percentChange}%)\nDays Ahead,${predictions.days}\nModel,${predictions.model}\nConfidence,${predictions.confidence}%\nRMSE,${predictions.rmse}\nMAE,${predictions.mae}\nR² Score,${predictions.r2}\nTimestamp,${predictions.timestamp}`;
    
    const blob = new Blob([csv], { type: 'text/csv' });
    const url = window.URL.createObjectURL(blob);
    const a = document.createElement('a');
    a.href = url;
    a.download = `prediction_${predictions.stock}_${new Date().getTime()}.csv`;
    a.click();
  };

  return (
    <div style={{ background: '#F8FAFC', minHeight: '100vh' }}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Geist:wght@400;500;600;700&family=Geist+Mono:wght@400;500&display=swap');
        
        body { font-family: 'Geist', sans-serif; }
        .font-mono { font-family: 'Geist Mono', monospace; }
        
        .transition-smooth { transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); }
        .shadow-card { box-shadow: 0 1px 3px rgba(0, 0, 0, 0.08), 0 1px 2px rgba(0, 0, 0, 0.04); }
        
        @keyframes slideUp {
          from { opacity: 0; transform: translateY(10px); }
          to { opacity: 1; transform: translateY(0); }
        }
        .animate-in { animation: slideUp 0.4s ease forwards; }
        
        .model-btn {
          transition: all 0.2s ease;
        }
        .model-btn:hover {
          transform: translateY(-2px);
          box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        .model-btn.active {
          border-left: 4px solid #2563EB;
          background: #EFF6FF;
        }
      `}</style>

      {/* Header */}
      <header className="bg-white border-b border-gray-200" style={{ boxShadow: '0 1px 0 rgba(0,0,0,0.05)' }}>
        <div className="max-w-7xl mx-auto px-6 py-6">
          <div className="flex items-center justify-between">
            <div>
              <h1 className="text-3xl font-bold text-gray-900">📈 StockPredict</h1>
              <p className="text-sm text-gray-600 mt-1">AI-Powered Stock Price Prediction Platform</p>
            </div>
            <div className="flex items-center gap-2 px-4 py-2 bg-blue-50 rounded-lg border border-blue-200">
              <Zap size={18} className="text-blue-600" />
              <span className="text-sm font-semibold text-blue-900">Powered by ML</span>
            </div>
          </div>
        </div>
      </header>

      <main className="max-w-7xl mx-auto px-6 py-8">
        <div className="grid grid-cols-1 lg:grid-cols-3 gap-8">
          {/* Left Column - Prediction Form & Chart */}
          <div className="lg:col-span-2 space-y-8">
            
            {/* MAIN PREDICTION FORM */}
            <div className="bg-white rounded-lg shadow-card p-8 border-t-4 border-blue-500 animate-in">
              <div className="flex items-center gap-3 mb-8">
                <div className="bg-blue-100 p-3 rounded-lg">
                  <Send className="w-6 h-6 text-blue-600" />
                </div>
                <div>
                  <h2 className="text-2xl font-bold text-gray-900">Predict Stock Price</h2>
                  <p className="text-sm text-gray-600 mt-1">Use AI to forecast future stock prices</p>
                </div>
              </div>

              <form onSubmit={handlePredict} className="space-y-6">
                {/* Stock Selection */}
                <div>
                  <label className="block text-sm font-semibold text-gray-700 mb-3">Select Stock Symbol</label>
                  <div className="grid grid-cols-2 md:grid-cols-4 gap-2 mb-4">
                    {popularStocks.map(stock => (
                      <button
                        key={stock.symbol}
                        type="button"
                        onClick={() => {
                          setSelectedStock(stock.symbol);
                          setCustomStock('');
                        }}
                        className={`px-4 py-2 rounded-lg font-semibold text-sm transition-smooth border-2 ${
                          selectedStock === stock.symbol
                            ? 'border-blue-500 bg-blue-50 text-blue-700'
                            : 'border-gray-200 bg-white text-gray-700 hover:border-gray-300'
                        }`}
                      >
                        {stock.symbol}
                      </button>
                    ))}
                  </div>
                  
                  <div className="relative">
                    <input
                      type="text"
                      placeholder="Or enter custom symbol (e.g., TICKER.NS)"
                      value={customStock}
                      onChange={(e) => {
                        setCustomStock(e.target.value.toUpperCase());
                        if (e.target.value) setSelectedStock(e.target.value.toUpperCase());
                      }}
                      className="w-full px-4 py-3 border-2 border-gray-300 rounded-lg text-gray-700 placeholder-gray-500 focus:outline-none focus:border-blue-500 transition-smooth"
                    />
                    <Info size={16} className="absolute right-4 top-4 text-gray-400" />
                  </div>
                  <p className="text-xs text-gray-500 mt-2">
                    Supports US stocks (AAPL, MSFT) and Indian stocks (RELIANCE.NS, TCS.NS)
                  </p>
                </div>

                {/* Prediction Days */}
                <div>
                  <label className="block text-sm font-semibold text-gray-700 mb-3">
                    Prediction Timeframe: <span className="text-blue-600 font-bold">{predictionDays} days</span>
                  </label>
                  <input
                    type="range"
                    min="7"
                    max="365"
                    value={predictionDays}
                    onChange={(e) => setPredictionDays(parseInt(e.target.value))}
                    className="w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer"
                  />
                  <div className="flex justify-between text-xs text-gray-500 mt-2">
                    <span>7 days (Short-term)</span>
                    <span>180 days</span>
                    <span>365 days (Long-term)</span>
                  </div>
                </div>

                {/* Model Selection */}
                <div>
                  <label className="block text-sm font-semibold text-gray-700 mb-3">Select ML Model</label>
                  <select
                    value={selectedModel}
                    onChange={(e) => setSelectedModel(e.target.value)}
                    className="w-full px-4 py-3 border-2 border-gray-300 rounded-lg text-gray-700 bg-white focus:outline-none focus:border-blue-500 transition-smooth font-medium"
                  >
                    {models.map(model => (
                      <option key={model.id} value={model.id}>
                        {model.name} ({model.accuracy}% accuracy)
                      </option>
                    ))}
                  </select>
                  <p className="text-xs text-gray-500 mt-2">
                    Ensemble model recommended for best results
                  </p>
                </div>

                {/* Predict Button */}
                <button
                  type="submit"
                  disabled={loading}
                  className="w-full bg-blue-600 hover:bg-blue-700 disabled:bg-gray-400 text-white font-bold py-4 rounded-lg transition-smooth flex items-center justify-center gap-3 text-lg"
                >
                  {loading ? (
                    <>
                      <div className="animate-spin h-5 w-5 border-3 border-white border-t-transparent rounded-full"></div>
                      Analyzing Market Data...
                    </>
                  ) : (
                    <>
                      <Send size={20} />
                      Predict Price Now
                    </>
                  )}
                </button>

                <p className="text-center text-xs text-gray-500 mt-4">
                  🔒 Your data is processed securely | No account required
                </p>
              </form>
            </div>

            {/* Chart */}
            {chartData.length > 0 && (
              <div className="bg-white rounded-lg shadow-card p-6 animate-in" style={{ animationDelay: '0.1s' }}>
                <h3 className="text-lg font-bold text-gray-900 mb-4">Historical & Predicted Price Trend</h3>
                <div style={{ position: 'relative', height: '400px' }}>
                  <canvas ref={chartRef}></canvas>
                </div>
              </div>
            )}
          </div>

          {/* Right Column - Results & Models */}
          <div className="space-y-6">
            
            {/* Prediction Results */}
            {predictions ? (
              <div className="bg-white rounded-lg shadow-card p-6 border-l-4 border-blue-500 animate-in">
                <h3 className="text-lg font-bold text-gray-900 mb-4 flex items-center gap-2">
                  <TrendingUp className="text-blue-600" size={20} />
                  Prediction Results
                </h3>

                <div className="space-y-4">
                  <div>
                    <p className="text-xs text-gray-600 uppercase tracking-wider mb-1">Stock</p>
                    <p className="text-xl font-bold text-gray-900">{predictions.stock}</p>
                    <p className="text-xs text-gray-500">{predictions.stockName}</p>
                  </div>

                  <div className="pt-4 border-t border-gray-200">
                    <p className="text-xs text-gray-600 uppercase tracking-wider mb-1">Current Price</p>
                    <p className="text-2xl font-bold text-gray-900">${predictions.currentPrice}</p>
                  </div>

                  <div className="pt-4 border-t border-gray-200">
                    <p className="text-xs text-gray-600 uppercase tracking-wider mb-2">Predicted Price ({predictions.days} days)</p>
                    <div className="flex items-baseline gap-2">
                      <p className="text-3xl font-bold text-blue-600">${predictions.predictedPrice}</p>
                      <div className={`flex items-center gap-1 px-3 py-1 rounded-full text-sm font-bold ${
                        parseFloat(predictions.change) >= 0
                          ? 'bg-green-100 text-green-700'
                          : 'bg-red-100 text-red-700'
                      }`}>
                        {parseFloat(predictions.change) >= 0 ? (
                          <TrendingUp size={14} />
                        ) : (
                          <TrendingDown size={14} />
                        )}
                        {predictions.change >= 0 ? '+' : ''}{predictions.change} ({predictions.percentChange}%)
                      </div>
                    </div>
                  </div>

                  <div className="pt-4 border-t border-gray-200 space-y-3">
                    <div className="flex justify-between">
                      <span className="text-sm text-gray-600">Confidence Score</span>
                      <span className="font-bold text-gray-900">{predictions.confidence}%</span>
                    </div>
                    <div className="w-full bg-gray-200 rounded-full h-2.5">
                      <div
                        className="bg-blue-600 h-2.5 rounded-full transition-all duration-500"
                        style={{ width: `${predictions.confidence}%` }}
                      ></div>
                    </div>
                  </div>

                  <div className="pt-4 border-t border-gray-200 space-y-2 text-sm">
                    <div className="flex justify-between">
                      <span className="text-gray-600">Model Used</span>
                      <span className="font-mono font-semibold text-gray-900">{predictions.model}</span>
                    </div>
                    <div className="flex justify-between">
                      <span className="text-gray-600">RMSE</span>
                      <span className="font-mono font-semibold text-gray-900">{predictions.rmse}</span>
                    </div>
                    <div className="flex justify-between">
                      <span className="text-gray-600">MAE</span>
                      <span className="font-mono font-semibold text-gray-900">{predictions.mae}</span>
                    </div>
                    <div className="flex justify-between">
                      <span className="text-gray-600">R² Score</span>
                      <span className="font-mono font-semibold text-blue-600">{predictions.r2}</span>
                    </div>
                  </div>

                  <button
                    onClick={exportPrediction}
                    className="w-full mt-4 flex items-center justify-center gap-2 px-4 py-2 bg-gray-100 hover:bg-gray-200 text-gray-700 font-semibold rounded-lg transition-smooth"
                  >
                    <Download size={16} />
                    Export as CSV
                  </button>
                </div>
              </div>
            ) : (
              <div className="bg-blue-50 border-2 border-blue-200 rounded-lg p-4 animate-in">
                <h4 className="font-semibold text-blue-900 mb-2 flex items-center gap-2">
                  <Info size={18} />
                  Ready to Predict?
                </h4>
                <p className="text-sm text-blue-800">
                  Fill in the prediction form and click "Predict Price Now" to get started. Results will appear here with confidence scores and performance metrics.
                </p>
              </div>
            )}

            {/* Models List */}
            <div className="bg-white rounded-lg shadow-card p-6">
              <h3 className="text-lg font-bold text-gray-900 mb-4">Available Models</h3>
              <div className="space-y-2 max-h-96 overflow-y-auto">
                {models.map(model => (
                  <button
                    key={model.id}
                    onClick={() => setSelectedModel(model.id)}
                    className={`model-btn w-full text-left px-4 py-3 rounded-lg border-2 transition-smooth ${
                      selectedModel === model.id
                        ? 'border-blue-300 bg-blue-50'
                        : 'border-gray-200 hover:border-gray-300'
                    }`}
                  >
                    <div className="flex items-center gap-3 mb-1">
                      <div
                        className="w-3 h-3 rounded-full"
                        style={{ background: model.color }}
                      ></div>
                      <span className="font-semibold text-gray-900">{model.name}</span>
                    </div>
                    <div className="text-xs text-gray-500 ml-6">
                      {model.accuracy}% accuracy rate
                    </div>
                  </button>
                ))}
              </div>
            </div>
          </div>
        </div>
      </main>
    </div>
  );
}
