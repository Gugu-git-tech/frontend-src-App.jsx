import React, { useState } from 'react';
import SpeakButton from './components/SpeakButton';
import ReadAloud from './components/ReadAloud';
import UploadImage from './components/UploadImage';
import ChatArea from './components/ChatArea';
import Monitoring from './components/Monitoring';

export default function App() {
  const [transcript, setTranscript] = useState('');
  const [chatHistory, setChatHistory] = useState([]);

  return (
    <div style={{ padding: 20, fontFamily: 'system-ui, sans-serif', maxWidth: 900, margin: '0 auto' }}>
      <h1>Accessibility Voice Assistant</h1>
      <div style={{ display: 'flex', gap: 20 }}>
        <div style={{ flex: 2 }}>
          <SpeakButton onTranscribed={setTranscript} />
          <ReadAloud text={transcript} />
          <UploadImage />
          <ChatArea chatHistory={chatHistory} setChatHistory={setChatHistory} />
        </div>
        <div style={{ flex: 1 }}>
          <Monitoring />
        </div>
      </div>
    </div>
  );
}
