import { useState } from 'react';
import { Card, CardContent } from '@/components/ui/card';
import { Button } from '@/components/ui/button';
import { Input } from '@/components/ui/input';
import { motion } from 'framer-motion';

const ToDoApp = () => {
  const [tasks, setTasks] = useState([]);
  const [newTask, setNewTask] = useState('');

  const addTask = () => {
    if (newTask) {
      setTasks([...tasks, { text: newTask, completed: false }]);
      setNewTask('');
    }
  };

  const toggleTask = (index) => {
    const updatedTasks = [...tasks];
    updatedTasks[index].completed = !updatedTasks[index].completed;
    setTasks(updatedTasks);
  };

  const deleteTask = (index) => {
    const updatedTasks = tasks.filter((_, i) => i !== index);
    setTasks(updatedTasks);
  };

  return (
    <div className='min-h-screen p-4 bg-gray-100'>
      <div className='max-w-xl mx-auto p-4 bg-white rounded-2xl shadow-lg'>
        <h1 className='text-2xl font-bold mb-4'>Shared To-Do List</h1>
        <div className='flex gap-2 mb-4'>
          <Input
            value={newTask}
            onChange={(e) => setNewTask(e.target.value)}
            placeholder='Add a new task'
            className='flex-grow'
          />
          <Button onClick={addTask}>Add Task</Button>
        </div>
        <div className='space-y-2'>
          {tasks.map((task, index) => (
            <Card key={index} className='flex items-center justify-between p-2'>
              <CardContent className='flex-grow'>
                <motion.div
                  initial={{ opacity: 0 }}
                  animate={{ opacity: 1 }}
                  className={`text-lg ${task.completed ? 'line-through text-gray-400' : ''}`}
                  onClick={() => toggleTask(index)}
                >
                  {task.text}
                </motion.div>
              </CardContent>
              <Button onClick={() => deleteTask(index)} className='ml-2'>Delete</Button>
            </Card>
          ))}
        </div>
      </div>
    </div>
  );
};

export default ToDoApp;
